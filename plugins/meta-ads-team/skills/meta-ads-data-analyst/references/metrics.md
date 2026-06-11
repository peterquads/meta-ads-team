# Metrics That Matter

Peter distrusts blended MER and platform ROAS. He steers by the new-vs-returning
split and contribution margin. Frame every number this way.

## The cardinal rule
Platform-reported ROAS overstates by roughly 2 to 3x (view-through, CAPI and pixel double-counting, iOS signal loss). Treat it as a directional optimization signal, never a P&L number. Correlation is also a weak proxy for incrementality, the real causal answer is geo-lift and halo studies (Meta lift on Amazon, on Google, on store revenue). That is the direction you point when ROAS cannot answer "is this actually working."

## The measurement stack (steer by these)
- **NCRPM**, New Customer Revenue per Mille = 1000 x CVR x New-Customer AOV. CPM flipped, revenue per 1,000 new visitors. The annual goal almost nobody sets: AOV up year over year while CVR holds flat or declines only enough that revenue per order still rises. Real example, over 3 years AOV +173%, CVR -35%, NCRPM +77%, the CVR drop did not matter.
- **NCMER**, New-Customer Revenue / New-Customer Ad Spend. Pull the new, engaged, existing spend split from Meta's breakdown (requires existing and engaged exclusions configured). Better than MER or aMER.
- **RCMER**, Returning-Customer Revenue / Returning-Customer Ad Spend. Keep new and returning as separate KPIs, reactivation is far more efficient than acquisition, blending hides it.
- **CMER**, Contribution-Margin Efficiency Ratio = Contribution Margin / Total Marketing Spend (strip COGS, pick and pack, card fees first). When marginal contribution margin goes negative, the next dollar is unprofitable even if blended still looks fine.
- **CPMr**, cost per 1,000 accounts-center reached. The core top-of-funnel KPI for net-new reach and market expansion.
- **AOV is the neglected ceiling lever.** Brands blame creative, targeting, or CPM when the real bottleneck is an AOV too low to make the math work at scale.

## Funnel decomposition (turning "CPA went up" into a fix)
CPA is roughly CPM/1000 x (1/CTR) x (1/CVR).
- CPM up, a delivery problem (auction, audience too narrow, frequency, seasonal).
- CTR down, creative fatigue or a weak hook, hand to the creative analyst.
- CVR down, a post-click problem (landing page, offer, price, audience, tracking), not the ad.
- Frequency up with CTR down, textbook fatigue.
Name the layer. That is what separates an analyst from a dashboard.

## The spend-ceiling lens (IAPM)
When the account stops scaling, it is usually not creative or bidding, it is the Initial Addressable Profitable Market. Meta serves a subset of TAM, the impulsive in-market slice, shrunk by required ROAS. The fix is a bigger market or a lower profitability threshold (raise AOV, improve margin), not more ads. Flag this when a brand is churning out creative and the ceiling will not move.

## Daily forecasting
Track 20+ metrics daily at channel and store level: projected spend by channel, new vs returning revenue targets, purchase volume, contribution margin or profit goal, CAC thresholds, landed cost per acquisition by source. Most brands operate blind. Day-of-week seasonality is real, MER by weekday varies per brand, so respect launch timing.

## Diagnostic metrics
Spend, impressions, reach, frequency, purchases and value, then derive ROAS, CPA, CPM, CTR (link), CPC, CVR, AOV. Use the account's reported attribution, do not silently mix windows. Note that Peter is shifting attribution off pure 7-day click toward 7-day click plus 1-day engaged and incremental as Meta redefines the click.

## Sources
Peter Quadrel (Odylic Media) measurement stack. Supporting context: Common Thread Collective, Triple Whale, Meta lift / Robyn. See repo SOURCES.md.
