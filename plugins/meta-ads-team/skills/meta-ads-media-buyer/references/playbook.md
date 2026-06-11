# Media Buying Playbook

How Peter runs the account. His rules are the defaults. Where the wider field
disagrees, that is noted at the end, but lead with this.

## First principles
- Every asset has an efficacious amount of spend, set by how much historical data exists for that product, creative, and offer. Budget structure exists to give each asset its efficacious spend, nothing more.
- CBO, ABO, ASC are just budget distribution strategies. Do not fetishize structure debates, the wrapper matters less than people think.
- Spend is Meta's confidence. A high-spend low-ROAS ad is often a top-of-funnel first-touch asset, not a loser. Check CPM, frequency, and new vs returning before killing.
- You do not break a spend ceiling with more creative, you expand the market. See the IAPM section.

## Account structure, organize by brand type first
- Aesthetic brands (emotion and identity led): organize campaigns by product category.
- Utility brands (problem solving): organize by persona or angle.

Campaign archetypes to build from:
1. Testing, ABO, lowest cost, one ad set per creative concept, 7-day click attribution.
2. Scaling, CBO with ROAS goal, migrate the top 10 to 20% of testing performers in.
3. Advanced scaling, best CBO performers promoted to Flexible Ad Format.
4. Partnership, separate ABO, one ad set per creator, winners migrate to CBO.
5. Catalog, DPA, standalone or inside testing.
6. BOF, $800+ AOV brands only, ABO targeting 180-day add-to-carts and engagers.
7. Reactivation, lapsed-customer list upload, ABO.
8. Reach or ATC, ATC objective for smaller brands, Reach for bigger spenders, standard at $100K+/month.

Consolidation target: under 30% of spend on the top 3 campaigns. CBO splits by angle or format, never by funnel position (CBO overspends the bottom funnel). ABO is the sandbox for net-new assets and audiences, it gives new creative a fair shot before it competes with winners.

## Targeting
Age, gender, country only. Advantage+ placements on. Formats 1:1, 4:5, 9:16. Customer exclusions applied. Do not use interest targeting to hit segments, segmentation happens in the creative messaging (the Cascade: Segment, Persona, Angle). Go broad and let the creative do the targeting.

## The 50-conversion budget math (this drives everything)
Aim for 50 conversions per week per campaign to exit learning. So:
- Required weekly revenue = 50 x AOV.
- Weekly spend = required weekly revenue / target ROAS.
- Daily = weekly / 7.
Example: $100 AOV, 3x target, weekly revenue $5,000, weekly spend about $1,667, daily about $238 minimum. Each asset should have headroom to spend up to roughly 1 AOV per day.
Budget allocation: 25 to 30% testing, 60 to 70% scaling, 5 to 10% promo and specialized. Run 3 to 4 creatives per $100/day of testing budget so each gets real spend.

## Bid strategy
- New account, new creative, new product, new offer, or new market: lowest cost, you need data and impressions first.
- Established account, proven assets, or promo periods: cost controls (cost cap or ROAS goal).

## Scaling
Scale +20% budget after 7 days of consistent performance. Winner criteria: 1 or more standard deviations above the mean for spend or revenue, or top 10 to 20% by revenue. For horizontal expansion, duplicate into new audiences at 50 to 70% of the original budget. For big planned bumps (sales, peaks), use create_budget_schedule rather than a manual spike.

## Kill rules
Cut when below break-even after spending 2 to 3x target CPA AND the asset is not feeding the funnel. Before you cut, recheck CPM, frequency, and the new vs returning split, the ad may be a first touch that makes retargeting work. Never kill on ROAS alone. Never make kill calls mid-learning-phase. $10 minimum spend for a valid test, 2 to 3x target CPA before any judgment. Iterate winners by default, and run net-new angle tests specifically to beat the current evergreen top-of-funnel.

## Cadence
7-day evaluation windows before decisions. Do not touch ads mid-learning. Weekly review for scaling, cutting, and fatigue. Brief 2 to 3 new concepts per week. Rotate new creative in and fatigued creative out rather than toggling ads on and off. Optimize creative, offer, and landing page before budget knobs.

## Learning phase
About 50 optimization events per ad set per 7 days to exit learning. Budget to clear it is roughly 5x target CPA per day per ad set. Do not stack edits during learning, every change can reset it.

## The spend-ceiling thesis (IAPM)
When a brand hits a wall, churning out 50 new ads bumps ROAS for a week and moves nothing, it just extracts more from a tapped market. The ceiling is set by the Initial Addressable Profitable Market. Meta serves you only a subset of your TAM, the impulsive in-market slice, shrunk further by your required ROAS. Two identical brands, one needing 5x and one needing 2x, have different IAPMs despite the same TAM, the 2x brand wins more auctions. To raise the ceiling, expand the market (a new Cascade segment, a new geo) or lower the profitability threshold (raise AOV, improve margin). The cheapest market expansion is partnership ads, renting creators whose followers already are the next segment. Peter is pushing partnership ads to 40 to 50% of Meta budget.

## Where the wider field differs (context, not the default)
The "+20% every few days or you shock learning" rule is debated. Cost-cap operators (Andrew Faris, Charley Tichenor) argue the cap governs delivery so you can scale harder. Tichenor keeps cost-capped spend under 20% of budget, Faris runs nearly all of it on cost controls. Peter's default above is lowest cost for testing, cost controls once proven. Reach for the cap debate only if the user runs cost caps.

## Sources
Peter Quadrel (Odylic Media) operating model. Supporting context: Common Thread Collective, Andrew Faris, Charley Tichenor, Nick Shackelford, Cody Plofker, Motion. See repo SOURCES.md.
