# Creative tagging schema (how to actually analyze creative)

The way to find patterns is not to read ads one by one. Tag every creative on a
consistent schema, then aggregate the tags against spend and revenue. This is the
schema and the method. For a large set, tag with a fast pass (a cheap model like
Haiku is ideal for batch). Pull the creative image through the MCP, and pre-extract
ground truth first so the tags are accurate, not guessed.

## Step 1, pull and pre-extract ground truth
- `get_ad_creatives` for headline, body, cta, and `effective_object_story_id`. `get_ad_image` for the image or video thumbnail.
- Read these directly rather than guessing them: textOverlay (OCR the on-image copy verbatim, keep casing), colors (the real hex codes), aspectRatio, and a productionQuality read from sharpness and resolution. Use them verbatim in the tags.

## Step 2, tag each creative on this schema
Run two passes, a visual pass (needs the image) and a copy pass (needs only the text), they can run in parallel.

**Strategy (Cascade + Brief Equation):** segment, persona, angle, concept, offer, category, collection, and emotion (one of: Trust, Excitement, Urgency, Calm, Sophistication, Humor, Inspiration, Confidence, Desire, Nostalgia).

**Audience and market (Breakthrough Advertising Grid, from the copy):**
- marketAwareness: Unaware, Problem Aware, Solution Aware, Product Aware, Most Aware.
- marketSophistication: L1 First in Market, L2 Competition Arrives, L3 Feature/Mechanism, L4 Elaboration/Experience, L5 Identification.
- funnelPosition: Awareness, TOF, MOF, BOF, Reactivation. demographics.

**Copy zones:** headline, bodyCopy, cta, textOverlay, marketingMoment (e.g. "Black Friday", or "Evergreen").

**Execution and production:** format (Static, Video, Carousel, GIF), aspectRatio, intendedPlacement (Feed, Story/Reels, Audience Network), style, productionQuality, layoutDescription, composition, colors, products, and 5 to 10 free-form tags for filtering.

**Differentiation and clarity scores, 0 to 100 (the per-creative diversity score):**
- creativeClarityScore: how clearly the value prop reads. Product-on-white with no text is 10 to 40, clear value prop with a strong hook and coherent hierarchy is 70 to 95, reserve 90+ for standout work.
- visualDifferentiationScore: would it stop a scroll in this vertical's feed. Generic category shot is 10 to 30, one distinguishing choice is 40 to 65, genuinely disruptive is 70 to 90.
- messagingDifferentiationScore: how unowned the copy angle is. "Shop now, premium quality" could live on any competitor and is 10 to 30, a distinct angle or voice is 40 to 65, specific and unowned is 70 to 90.
Each score gets a one or two sentence reason. Never score 0 as a cop-out, give an honest estimate.

## Step 3, aggregate (this is where the insight is)
Read the tags against money, not the ads:
- Group spend and revenue by angle, by emotion, by funnelPosition, by format, by persona. The winning angle or emotion is the pattern to brief more of.
- Diversity gaps: count unique values per dimension across the live set. If 8 of 10 ads share an angle or an emotion, that is the gap, and it is a math problem, not a fatigue problem.
- Cross the Breakthrough Grid: if you only speak to Most Aware while Problem Aware sits untouched, that is a Cascade level to open.
- Use the differentiation scores to find weak links: a high-spend ad with low visualDifferentiation is winning on budget, not craft, and will fatigue fast.

## What the analyst hands back
The scorecard, plus the patterns written as brief-ready instructions ("make more: [angle] + [emotion] for [persona] at [funnel position]"), the diversity gaps to fill, and the fatiguing assets split into refresh vs retire.
