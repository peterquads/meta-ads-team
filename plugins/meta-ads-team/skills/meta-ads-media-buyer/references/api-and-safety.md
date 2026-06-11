# Meta Ads MCP, write tools, Meta API fields, and the safety protocol

Read this before executing any change. Tool signatures are from the `meta-ads-mcp`
source (Pipeboard). The same tools may surface in your client with an `mcp_meta_ads_`
prefix, match whatever names your MCP exposes.

## Write-tool parameters (the ones that move money)

**`create_campaign`**, required: `account_id`, `name`, `objective`. Optional: `status` (defaults `PAUSED`), `special_ad_categories: [..]`, `daily_budget`/`lifetime_budget` (cents), `bid_strategy` (default `LOWEST_COST_WITHOUT_CAP`), `bid_cap`, `spend_cap`, `campaign_budget_optimization: bool`, `buying_type`.

**`update_campaign`**, required: `campaign_id`. Optional: `name`, `status`, `daily_budget`, `bid_strategy`, `bid_cap`, `spend_cap`, `objective`, `special_ad_categories`.

**`create_adset`**, required: `account_id`, `campaign_id`, `name`, `optimization_goal`, `billing_event`. Optional: `status` (default `PAUSED`), `daily_budget`/`lifetime_budget` (cents), `targeting: {..}`, `bid_amount` (cents), `bid_strategy`, `start_time`/`end_time`, `promoted_object`, `is_dynamic_creative`, `frequency_control_specs`, `attribution_spec`.

**`update_adset`**, required: `adset_id`. Same optional surface (this is how you **scale**: change `daily_budget`; **pause**: `status="PAUSED"`).

**`create_ad`**, required: `account_id`, `name`, `adset_id`, `creative_id`. Optional: `status` (default `PAUSED`), `bid_amount`.

**`update_ad`**, required: `ad_id`. Optional: `name`, `status` (the most common write, **pause a loser** / **activate**), `bid_amount`, `creative_id`.

**`create_ad_creative`**, required: `account_id`. Optional (40+): `image_hash`, `page_id`, `link_url`, `message`/`messages`, `headline`/`headlines`, `description`/`descriptions`, `video_id`, `call_to_action_type`, `object_story_id`, `instagram_actor_id`, `dynamic_creative_spec`, …

**`upload_ad_image`**, required: `account_id` + one of `file` (local path) or `image_url`. Returns an `image_hash` for the creative.

**`create_budget_schedule`**, required: `campaign_id`, `budget_value` (cents), `budget_value_type` (`ABSOLUTE`/`MULTIPLIER`), `time_start`, `time_end` (unix). Use this for planned sale/peak bumps instead of manual spikes.

**`get_insights`**, pass an id (`account_id`/`campaign_id`/`adset_id`/`ad_id`) + `time_range`, `level`, `breakdown`. Always read before you write.

**Targeting tools:** `search_interests(query, limit)`, `get_interest_suggestions(interest_list)`, `search_behaviors`, `search_demographics`, `search_geo_locations(query)`, `estimate_audience_size(...)`. (Note: interest *validation* is folded into `get_interest_suggestions`/`estimate_audience_size`, there's no separate validate tool.)

## Meta API fields you must get right

- **Budgets are in MINOR currency units (cents for USD).** `daily_budget: 5000` = **$50.00/day**, not $5,000. Triple-check this on every budget write, it's the most dangerous mistake. Confirm the account currency (a few zero-decimal currencies like JPY/TWD use whole units).
- **Objective enums** (set on campaign): `OUTCOME_SALES` (purchases, the DTC default), `OUTCOME_LEADS`, `OUTCOME_TRAFFIC`, `OUTCOME_ENGAGEMENT`, `OUTCOME_AWARENESS`, `OUTCOME_APP_PROMOTION`. The ad set's `optimization_goal` must be compatible (Sales → `OFFSITE_CONVERSIONS`).
- **`special_ad_categories`**, required for housing/employment/credit-finance/social-issues/politics ads. Declaring one **restricts targeting** (no age/gender narrowing, no zip-radius). Omitting it on a regulated vertical is a policy violation. Use `["NONE"]` for standard ecommerce.
- **`status`**: `ACTIVE` / `PAUSED`. New objects default to `PAUSED` in this MCP, you must explicitly activate. `effective_status` (read-only) rolls up parent pauses + review state.
- **Targeting spec** (the `targeting` dict): `{"geo_locations": {"countries": ["US"]}, "age_min": 18, "age_max": 65, "genders": [1,2], "flexible_spec": [{"interests": [{"id": "...", "name": "..."}]}]}`. **Broad** = geo + wide age, drop `flexible_spec`. `genders`: 1=male, 2=female, omit=all.
- **Advantage+ Shopping (ASC):** the legacy `smart_promotion_type` flag is deprecated in Marketing API v24/v25 and the MCP doesn't expose it. Create an `OUTCOME_SALES` campaign with broad/Advantage+ audience settings rather than relying on the old flag. If unsure how the current account creates ASC, say so and confirm with the user.

## THE EXECUTION PROTOCOL (never skip)

These tools spend real money in a live account. A wrong budget edit (cents!) or a bad
targeting change can burn thousands before anyone notices. Speed on analysis, deliberation on action:

1. **READ** the current state of everything you'll touch (`get_*` + `get_insights`). Never edit a line item you haven't just looked at.
2. **PROPOSE a change-set**, itemized: each change with before → after, the dollar impact, and the reason. Total the net daily-budget delta. Call out anything that re-enters learning. **Do not call a write tool yet.**
3. **CONFIRM**, wait for an explicit yes. "Approve all", "do 1 and 3", "change the budget on 2 first" all count. A question or silence does not. Honor partial approvals exactly.
4. **EXECUTE & VERIFY**, make approved writes one at a time; after each, read it back (`get_*_details`) to confirm it landed and the value is right (especially budgets in cents). Report a short receipt of what changed.

### Guardrails baked into every proposal
- **Confirm budget units.** State the dollar value AND the cents value you'll send.
- **Scale gently** on budget-optimized campaigns (~20-30% per move); for aggressive scaling propose duplicate-and-scale or a budget schedule.
- **Second confirmation** if a change-set's net budget delta is large vs current account spend (>~25%).
- **Don't kill on thin data** (see playbook kill rules). Put the evidence in the reason.
- **Never invent IDs.** Every id comes from a read call in this session.
- **Respect `special_ad_categories`**, ask if the vertical might be regulated.
