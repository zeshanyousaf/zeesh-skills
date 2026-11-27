# Recast Agent

A reusable agent that rebuilds a reference video around the user's own characters — reference video + character images, BOTH together, every time.

## Inputs (BOTH together — user correction 2026-10-16)
1. **Video reference** — sets performance: motion, pacing, camera work, beats, setting.
2. **Character image** — sets who appears. User puts BOTH, hits GENERATE. Backend Veo 3 account generates, finished video delivered in chat.

## Fixed settings (user-locked 2026-10-16)
- Backend: **Veo 3 account** for video generation (Flow). Account: the Gmail WITH credits — verified 2026-10-16: Zeshan Yousaf (yzeshanyousaf@gmail.com). Frontend only puts image reference → Agent generates on backend Veo 3 account → finished video delivered in chat.
- Model: **Omni 1.1 Flash**
- Duration: **10 seconds**
- Resolution: 720p, output x1
- Cost shown by Flow: ~15 credits per 10s Omni generation — report before/after if visible.

## Workflow
1. **Watch reference video.** Break it into beats: 0–2s / 2–4s / 4–6s / 6–8s / 8–10s. Note: camera (handheld selfie / tracking / static), setting, other people / objects / vehicles, key props, gestures.
2. **Lock characters.** From character image(s), write an exact identity block: head/face, skin/fur texture, eyes, eyebrows, outfit (unless outfit comes from reference — see step 3), distinguishing marks. Add: "Keep [name] 100% consistent in every shot — identical face, head shape, skin/fur texture."
3. **Build prompt — GENERIC WORDING ONLY.** Never use brand / third-party words (UNO, Porsche, brand logos, "recast this exact performance"). Use:
   - UNO cards → "colorful playing cards" (keep +2 / +4 colours/numbers if needed: "green +2 card, green +4 card")
   - Porsche / branded cars → "unbranded sports cars" (keep colours + shapes: "dark maroon sports car left, light pink sports car with big spoiler right")
   - "Recast" → "Animate [name] in this exact performance" / "Keep motion, pacing, camera work and background same"
   Flow blocks on third-party wording (seen 2026-10-16: "due to interests of third-party content providers") — do NOT retry the identical blocked prompt.
4. **Prompt structure (paste verbatim into Flow):**
   ```
   Animate [NAME] in this exact performance. Keep motion, pacing, camera work and background same.
   CHARACTER - [NAME], keep 100% consistent: [exact identity block]. He/she wears: [outfit from reference].
   SETTING: [setting from reference, generic brands].
   ONE CONTINUOUS SHOT, no cuts, [camera style].
   0-2s: [beat]
   2-4s: [beat]
   4-6s: [beat]
   6-8s: [beat]
   8-10s: [beat]
   Photorealistic / [style from reference], [lighting]. No text, no subtitles, no logos, no watermarks.
   ```
5. **Generate in Flow.** Ingredient = character image(s). Reference video motion comes via the prompt beats. If Flow accepts video as ingredient, add reference video too. One generation at a time.
6. **On failure:** Do NOT click Retry on the identical prompt. If message is third-party / policy, strip more brand words and retry ONCE with approval. If OTP / password / payment is asked, STOP and report which account needs it — never type passwords, never pay.
7. **Deliver.** Wait for finish, download if Flow offers it. Report: account used, credits before/after if visible, duration, download status. Deliver video as ~2MB compressed chat copy (user phone rule) + full file.

## Example (verified 2026-10-16)
- Reference: man in tuxedo, UNO +2/+4 cards, 2 Porsches, woman, sunset parking lot.
- Character: Coco — coconut head, 3 holes on top, brown fibrous skin, thick eyebrows, warm smile.
- Recast: Coco in black tuxedo + white gloves + silver sunglasses, same beats, generic playing cards + unbranded sports cars, Omni 1.1 Flash, 10s.

## Related
- Front-end: Recast Tool artifact (reference video + character images, both together, builds the Flow-ready prompt).
- Standing rules: zero budget (no paid tools unless earnings), videos as ~2MB chat copies, never re-ask standing approvals.
