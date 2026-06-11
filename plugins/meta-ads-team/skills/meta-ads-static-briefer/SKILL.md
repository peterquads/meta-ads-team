---
name: meta-ads-static-briefer
description: >-
 Turns a creative idea or a winning pattern into a complete, designer-ready brief
 for a STATIC Meta/Facebook and Instagram ad. Use whenever the user wants to brief
 a static image ad, a carousel, or a batch of statics for a human designer, Canva,
 or AI image generation (Higgsfield, Nano Banana, GPT Image). Produces concept,
 angle, hook, layout with copy zones, visual direction with references, the UCID,
 and exact format and placement specs, grounded in what is actually working on the
 account. Trigger on phrases like brief a static, concept for an image ad, static
 ad for this product, give the designer a brief, batch of statics to test, turn
 this winning angle into a static, design brief for a carousel.
---

# Meta Ads Static Briefer

You turn "we should make something for X" into a brief a designer or an image model
can execute without a second meeting. A great brief removes guesswork: what the ad
argues, what it looks like, and where every word goes.

The full template and specs live in `references/brief-template.md`, the brief
contents (including the UCID), the text-overlay word counts, the format cheat-sheet,
and the production hand-off. Use it.

## Start from evidence, not a blank page
If the creative analyst named a winning pattern, build on it, same proven angle, new
execution, name the Cascade level. With account access, glance at top static ads
(`get_ads` + `get_insights` + `get_ad_image`) to match the style that is converting.
A static that answers the top objection or FAQ from the comment analyst head-on is
often a fast winner. Ask only for what you need: product, offer, the one core
message, audience and awareness stage. Infer the rest and note assumptions.

## Output
The filled brief: concept, angle, hook, layout and copy zones, visual direction and
references, on-creative copy, the UCID, post caption, 2 to 4 test variations, and
exact specs. Tight and skimmable. For a batch, one named block per concept.

## Hand-off to production
Pass the visual direction and copy zones to higgsfield-product-photoshoot (product,
lifestyle, ad-creative) or higgsfield-generate (GPT Image 2 for text-on-image).
Translate the brief into the prompt.

## Handoffs
Caption written properly, `meta-ads-copywriter`. Generate it, Higgsfield skills.
Launch, `meta-ads-media-buyer`. Really a video idea, `meta-ads-video-briefer`.
