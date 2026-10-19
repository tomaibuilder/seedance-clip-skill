# Ad prompt templates (Seedance 2.5)

Brand-agnostic. Fill the `<...>` slots from the brand brief (see demo-recipes.md, "Brand brief"). Keep under about 500 words. Aspect ratio, duration and resolution are API parameters, not prompt text (official optimizer rule). The template headers may still say "9:16" to guide the layout words.

Sources: BytePlus guide, official launch prompts, Atlas skill, LearnPrompt/awesome-seedance templates. Untested on Tom's account.

## Ad ideas (menu for Job 0, idea batch)
Street interview or blind test. FaceTime-style confession. Get-ready-with-me or day-in-the-life. Podcast or founder clip. Cinematic mini-story around one benefit. Comedy scene with an unexpected visual in the first 5 s. Before and after, problem and solution. Product demo with macro shots or an impossible camera move. Challenge, comparison or objection-busting. Localised version with a new hook, character or setting.
For each idea give: hook (0-3 s), format, selling angle, rough shot plan.

## Product rules (every ad)
- 2-5 clean reference images per product (front, side, in use), role `reference_image`. Bind each by number in the prompt.
- Add: `Keep the product exactly as in Image N, no redesign. No extra logos or text.`
- Printed text on a product or cover is garbled often. Supply the cover or label as a reference image, or overlay in post.
- Claims: only what the brand brief supports. No invented prices, discounts or results.
- Describe product moves as: initial state, one operation, visible result.
- Real human faces in uploaded images are rejected. Use hands, POV, product-only, preset digital characters or `asset://` authorised assets.
- 3-6 s per beat. About 4 state changes per 15 s. Hook in 0-3 s. One camera move per shot.
- Repeat the 2-3 key locks at the end of the prompt (product identity, text spelling, exclusions).

## A. UGC product ad (9:16, 15 s)
```
Style: Vertical UGC video shot on iPhone, handheld, arm's-length wobble, small refocus moments, natural window light, native creator-shot realism. No cinematic lighting, no polished commercial styling.
Assets: Image 1 = <product, front>. Image 2 = <product, in use>. Image 3 = text card "<2-4 words>".
Summary: <creator type, hands or POV only> shows <product> in <setting> and <does one thing>, UGC review, handheld.
0-3s: Close-up, <hook action with the product>. Text appears top center: 【<hook, 1-4 words>】, referring to Image 3.
3-7s: <unbox / use / demo step>. End state: <visible result>.
7-11s: <proof or detail shot, macro>. 
11-15s: <product placed back, final hold>. Text appears bottom center: 【<CTA, 1-3 words>】.
Audio: Voice (<tone>, <language>): {<one line from approved copy>}. Sound effects: <list>. Music: <none or style>.
Constraints: Keep the product exactly as in Image 1, no redesign. No logos other than on the product. No subtitles other than the 【】 text listed. Visible text in the last frame: <CTA>.
```

## B. Product commercial (16:9 or 9:16, 10-15 s)
```
Style: Cinematic product commercial, <colour grade>, shallow depth of field, <light>, slow premium pace.
Assets: Image 1 = hero product.
Summary: <product> <event> in <environment>, premium commercial, slow push-in.
0-3s: Extreme close-up of <detail>, camera pushes in slowly. End state: <product edge lit>.
3-7s: Orbit around the product on a <surface>. <one moving element: particles, water, light sweep>.
7-12s: Wide reveal, product centered. Text appears center: 【<brand name>】, bold <font feel>, holds still.
Audio: Music: <style, strong rhythm>. Sound effects: <list>.
Constraints: Keep the product exactly as in Image 1. No subtitles other than the 【】 text listed.
```

## C. Kinetic-type brand sting (8-15 s, text-first)
Official pattern: one block of about 1.2 s per word, background plus arrival plus exit. No hard cuts.
```
A seamless creative text animation. Each word lasts about 1.2 seconds. Transitions use text dissolving, deforming or drifting into particles, no hard cuts. Music has a clear rhythm and strong beat hits.
0-1.2s English "<WORD 1>": <background look>. <how the letters arrive, e.g. rough crayon strokes write the uppercase word letter by letter>. The text dissolves into particles.
1.2-2.4s English "<WORD 2>": The particles reassemble into the word. <new background>. <colour or light effect across the letters>.
2.4-3.6s English "<WORD 3>": ...
<last block>: Brand name 【<BRAND>】 locks center, holds still for 1 second. Visible text in the last frame: <BRAND>.
Constraints: Only the words listed appear as text. Exact spelling as quoted.
```
Add: logo as `reference_image` for the last block if the logo must be exact. Else add the logo in post.

## D. Static ad to animated ad (image-to-video)
```
Image 1 is the first frame, the finished ad. Keep all text exactly as in Image 1 and hold it still. 
0-3s: Camera pushes in slowly. <product> rotates 15 degrees. A soft light sweep crosses the product.
3-8s: <background elements> drift. <one secondary motion>. 
Constraints: No new text. No redesign of the product or layout.
```
Task type: `first_frame` with `ratio: "adaptive"`. Cannot be mixed with reference roles. Image ratio must be 0.4-2.5.

## E. Flash-sale ad (9:16, 15-30 s)
```
Vertical high-contrast realistic style, <product>. 
Shot 1: Close-up, product floats and rotates against a neon gradient background, camera pushes in fast. (Strong rhythmic electronic drumbeat starts) <power-on sound>. 【<OFFER, 2-4 words>】.
Shot 2: ...
Constraints: Captions appear rhythmically with shot changes, high-contrast promotional feel. No subtitles other than the 【】 text listed.
```
(Adapted from the Atlas example. The original said "no subtitles" and wanted captions. That contradicts.)
