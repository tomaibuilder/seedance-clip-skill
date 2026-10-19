# YouTube demo recipes (sponsor or client brand)

Four ready-made demos for the video Tom is recording. All are brand-agnostic. Fill the brand brief first. Every request still follows the approval gates in SKILL.md section 0. Nothing here is tested yet: the first run is the test. Log what spells correctly and what does not in "Lessons".

## Brand brief (ask before any recipe, ask only what is missing)
- Brand name, product, one-line offer
- Approved copy only: headline, 1-2 hooks, CTA, any price or claim, exact casing. Do not invent claims, prices or offers. If the brand supplied copy, use it word for word.
- Assets: product images (2-5), logo file, brand colours, fonts, any "do not" list. Real faces are rejected.
- Platform and ratios: 9:16, 1:1, 16:9
- Sponsored-post folder: `Content Creation/Sponsored Posts/[Brand - Month Year]/`, start at its `00_START-HERE.md` if it exists. Ask Tom where this brand's clips should be saved (this folder or `Content Creation/Seedance Clips/`). Do not decide alone.
- Copy gate: read `VOICE.md` and `Copywriting/Guides/corrections.md` for any copy Tom writes. Sponsor-approved copy stays as supplied. Run the humanizer on Tom's own lines only.
- Hosting: asset URLs must be public. Uploading a file to public storage is outward-facing. Ask Tom first, and name the file and place.

## Request counts (state these at approval time)
Each clip is 1 draft (480p) plus 1 final (1080p) = 2 requests. Max 3 tasks at once. Never expand a batch.

| Recipe | Requests | Other paid calls |
|---|---|---|
| 1 Static ad to animated ad, Variant A only | 2 | 1 image (ai-image-factory, its own approval) |
| 1 plus Variant B (optional) | +2 | none |
| 2 Kinetic brand sting | 2 | none |
| 2 plus naive-prompt comparison (optional) | +1 (draft only) | none |
| 3 UGC product ad | 2 | none |
| 4 Same ad, 3 ratios | 6 (3 drafts, 3 finals) | none |
| All four, no options | 12 | 1 image |
| All four, with both options | 15 | 1 image |

Run order for the video: 2 (fast, pure text, shows the ladder), 1 (before and after), 3, 4. Test one draft first. Wait for Tom to review before the next.

## Recipe 1. Static ad image to animated ad
Demo story: the still on screen, then it moves, text stays correct.
1. Brief and approved headline (max 4 words on the image).
2. Make the still with `ai-image-factory` (separate approval, its own rules). Image models usually render exact text better than video models. Check spelling on the still. 9:16, no real faces.
3. Host the PNG (ask Tom). Public URL.
4. Variant A (faithful): task `first_frame`, `ratio: "adaptive"`, template D in ad-templates.md. Text is in the frame from second 0 and holds still. Motion is camera, product and background.
5. Variant B (text moves in): still as `reference_image` text card plus product images, template A or B with the text beat from the ladder. More motion, less faithful.
6. Draft at 480p. Check text letter by letter at 0 s, mid, last frame. Text that morphs mid-clip = hold-still wording, shorter beat, or rung 5.
7. Approve final. Download at once (24 h).
On-screen beat: still, then draft, then final, side by side.

## Recipe 2. Kinetic-type brand sting
Demo story: pure animated text, and how the ladder fixes spelling.
1. Take the brand name plus a 3-4 word tagline from the approved copy. Max 3-4 words total.
2. Template C. One block per word, about 1.2 s. 8-10 s total. Ratio per platform.
3. Draft. Spell-check. If a letter is wrong: rung 2 (letter reveal), then rung 3 (text card).
4. Logo: reference image in the last block, or add in post (rung 5).
Optional demo beat: run the same copy with a naive prompt (no ladder) as one extra draft, to show garbling. That is 1 extra request. Ask Tom first.

## Recipe 3. 9:16 UGC product ad
Demo story: handheld creator-style ad from product photos.
1. 2-5 product images as `reference_image`, task `reference`, `omni_reference_task_type: "reference"`.
2. Hands or POV only. No real face (rejected). Or a preset digital character.
3. Template A. 15 s, `generate_audio: true` if there is a voice line. One approved line only. Short caption lines in 【】, 1-4 words, max 3.
4. Draft. Check product shape and colour against the reference. Check caption spelling. Check no extra logos.
5. Final after Tom approves.

## Recipe 4. Same ad, three aspect ratios
Demo story: one brief, every placement.
1. Pick a base that uses text-to-video or reference mode: template A, B or C (recipe 2 or 3). Do NOT use recipe 1 Variant A: `first_frame` locks `ratio` to `adaptive`, so the ratio follows the image.
2. Send the prompt with `ratio` set to 9:16, 1:1 and 16:9. Change the orientation words ("Vertical", "horizontal") and the text positions in each prompt to match the ratio. Do not send "Vertical" with `ratio: 16:9`. Three drafts at once is the account limit (3 concurrent tasks).
3. Honest note: new generation per ratio gives similar but not identical footage. For the exact same footage in a new ratio, use Reference mode with the full shot timeline (Edit mode is not for ratio change; the official docs call the conversion unstable).
4. Layout rule for text (general ad practice, not from the docs): keep text in the centre area, away from the edges and the bottom 20% in 9:16 where platform UI sits. Name the position per ratio in the prompt.
5. Approve finals one by one, or "yes, N clips" for all three.

## Per-clip files
`Content Creation/Seedance Clips/YYYY-MM-DD-<brand>-<recipe>/`: `prompt.md`, `request.json` (no key), video, `last-frame.jpg` if requested. If the brand is a sponsor, copy the final to the sponsored folder only if Tom asks. State the full path every time.

## Run sheet for the recording
For each recipe: show the brief, the prompt, the approval block, the draft, the spell-check, the final. One clip per take. Keep rejected drafts. A failed draft with the fix applied is good content.
