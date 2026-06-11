---
name: meta-ads-team
description: >-
 The index for a full AI Meta Ads agency team that runs on the Meta Ads MCP. Use
 when the user asks what these skills can do, which one to use, wants an end-to-end
 pass on an account (analyze, decide, brief, write, report), or says things like
 run the whole team on this account, who should handle this, or what can the meta
 ads skills do. Routes work to the right specialist: data analyst, creative
 analyst, comment analyst, media buyer, copywriter, static briefer, video briefer,
 and reporter.
---

# Meta Ads Team, your AI media-buying agency

A roster of specialist skills that share one backend, a Meta Ads MCP. Each owns one
job a real performance team would own. Use this skill to route work or run a full pass.

The shared voice and the operating principles live in `references/voice-and-principles.md`.
Read it when running any specialist. The short version: creative is the primary lever,
every asset has an efficacious amount of spend, segmentation happens in the creative
not the targeting, you break a ceiling by expanding the market (IAPM), and money
moves need a yes. Voice is direct and data-led, with no em dashes.

## The roster
| Skill | Role | Use it when |
|---|---|---|
| `meta-ads-data-analyst` | Performance analyst | how did we do, diagnose ROAS/NCMER/CPA moves, breakdowns |
| `meta-ads-creative-analyst` | Creative analyst | which ads win and why, tag-and-aggregate, fatigue, patterns |
| `meta-ads-comment-analyst` | Voice of customer | what are people saying, objections, FAQs, social proof |
| `meta-ads-media-buyer` | Account operator | launch, scale, pause, reallocate, executes with approval gates |
| `meta-ads-copywriter` | Copywriter | primary text, headlines, hooks, variants |
| `meta-ads-static-briefer` | Creative strategist | designer or AI brief for a static or carousel |
| `meta-ads-video-briefer` | Creative strategist | script and shot list for a video or UGC ad |
| `meta-ads-reporter` | Account manager | client-ready daily and weekly recap |

## The loop
Analyze (data, creative, comment analysts) then decide and act (media buyer) then
create (briefers, copywriter) then launch (media buyer) then report (reporter). For
an end-to-end request, run that sequence and present one consolidated output,
otherwise pick the single matching specialist.

## The frameworks the team runs on
Cascade Targeting (Segment to Persona to Angle, via messaging). The Brief Equation
(Persona x Angle x Format). IAPM and TAPM (the spend-ceiling thesis). The measurement
stack (NCRPM, NCMER, RCMER, CMER, CPMr). The Breakthrough Advertising Grid (awareness
x sophistication, per persona). The creative tagging schema and the 20-variable
diversity system. Each specialist's references carry the detail.

## Ad naming and the UCID
Every creative gets a UCID, a cross-platform creative id, so the same asset is
trackable across Meta, Google, and AppsFlyer. Ad names encode the creative variables
in order (UCID, iteration or net-new, product, offer, persona, angle, concept, funnel,
format, message type, production, ratio) so any single variable can be analyzed
later. Keep the variables consistent or variable-level analysis breaks.

## Setup (one-time)
Assumes a connected Meta Ads MCP. If the tools are not available, point the user to
install the public meta-ads-mcp and authenticate (free token at pipeboard.co/api-tokens),
then confirm with `get_ad_accounts`. Each skill takes an account id, ask once, reuse it.

## Team-wide guardrails
Read before write. Money moves need an explicit yes (see `meta-ads-media-buyer`).
Numbers come from the MCP, not memory, never invent a metric or a comment. One brand
or account at a time unless asked for a rollup. Frameworks are credited in the repo SOURCES.md.
