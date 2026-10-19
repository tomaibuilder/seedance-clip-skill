# Text in Seedance 2.5 video

Researched 2026-10-06. Sources: BytePlus 2.5 prompt guide (ModelArk/2607689, "Text spelling errors"), official launch prompts (github.com/EvoLinkAI/awesome-seedance-2.5-guide), Atlas skill (AtlasCloudAI/awesome-seedance-2.5-prompts-skills), pletor.ai blog. NOT yet tested on Tom's account. Log results in SKILL.md "Lessons".

## The facts
- Text is not reliable. Official known failures: swapped letters (E becomes A or I), wrong Chinese characters. Third-party: dropped list items, garbled small text.
- Subtitles can appear even when told "no subtitles". Better in 2.5, not removed.
- No guarantee for exact text. The official optimizer (sd25-pe) says so too.

## The ladder (stop at the first rung that spells the copy correctly on the draft)

| Rung | Method | Prompt wording |
|---|---|---|
| 1 | Short text in the prompt, 1-4 words | `Large bold white sans-serif text appears bottom center: 【SAVE 30%】.` |
| 2 | Letter-by-letter reveal (official fix) | `The letters S, A, V, E appear one by one in sequence.` |
| 3 | Text card as reference image (official fix) | Upload PNG of the exact text as `reference_image`. `Text appears bottom center: 【SAVE 30%】, referring to Image 2.` |
| 4 | Kinetic type, one block per word | `1.2-2.4s: <background>. <how the word arrives>. <how it leaves>.` |
| 5 | Clean footage, text added in post | `No subtitles.` Then `video-use` skill or an HTML overlay adds headline, price, logo, CTA |

Use rung 5 for: long copy, prices, legal lines, phone numbers, URLs, logos. Do not fight the model for those.

## Rules
- Max 3-4 text items per 15 s. One text line per beat, with start second and position.
- Style goes in the prompt: font feel (bold sans, serif, hand-painted), colour, size, position.
- Motion words that work: fade, slide, scale, dissolve, deform, particle scatter, pixelate, written stroke by stroke. One element at a time, staggered 0.3-0.5 s (third-party blog, untested). Say the text holds still after it lands.
- Transitions between words: dissolve, deform or particles. No hard cuts in kinetic type.
- End the prompt with a literal list of all text visible in the last frame (third-party, untested).
- Never write `No subtitles` in a prompt that wants captions. They contradict. Write: `No subtitles other than the 【】 text listed.`
- Never repeat spoken words as text unless wanted. A dialogue line followed by the same words triggers burned-in subtitles.
- Reference videos with burned-in subtitles override `no subtitles`. Clean them first.
- No text on storyboard panels.
- Resize reference images to no larger than the output resolution (fingerprint artifacts).
- Quote exact text with the exact casing. Say the language when not English.

## Check on every draft
1. Pause the draft. Read each text item letter by letter against the approved copy.
2. Count the text items. Missing item = dropped (common).
3. Check text timing against the plan.
4. Any error: go up one rung. Do not resend the same prompt hoping for luck.
5. The final reuses the draft settings, so a draft spelling error will likely appear in the final (inference, not confirmed).

## Failure to fix table

| Symptom | Fix |
|---|---|
| Wrong letter | Rung 2 or 3, shorten the word list |
| Text appears that was not asked for | Remove repeated dialogue words, add `No subtitles other than the 【】 text listed`, check reference clips for burned-in subs |
| Dropped text items | Fewer items per clip, one item per beat, or rung 5 |
| Gibberish small text on product or UI | Supply the real asset as a reference image, or overlay in post |
| Text drifts or morphs during motion | Hold the text still after it lands. Shorter beats. Rung 3 or 5 |
| Timeline drifts about 2 s over 15 s (Atlas) | Stage the prompt with a visible end state per beat |
| Middle beats dropped | Max about 4 state changes per 15 s |
| Long negative list not working | The official guide prefers positive wording. Test a negative list once before adopting |
