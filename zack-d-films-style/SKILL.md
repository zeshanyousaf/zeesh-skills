# Zack D. Films Style — 3D Animated Fact Shorts

Use this skill when Zeesh asks for a fact short or explainer "Zack D Films ki tarah", a WhoaWire video, or to analyze/copy that format. The worked frame-by-frame example lives in `frame-by-frame-bookshelf-door.md` in this folder — read it before building.

## The channel (checked 27 Nov 2026)

- Zack D. Films (@ZackDFilms), tagline "A Collection of Things I Find Interesting". Created 7 June 2021.
- ~29.7M subscribers, ~83.8B total views, 4,000+ videos, uploads 4–5 Shorts a day. Faceless — the creator never appears; only narration.
- Breakout video: "This is why the Titanic is Disappearing" (4 Mar 2022). Most viewed: "How Stitches Work" (~255M views).
- 100% CGI since late 2023 (earlier videos used stock/real footage). His team pipeline: Blender + Cascadeur (physics-assisted character animation) + After Effects, heavy templates, contract animators. Zeesh's route is AI generation tools following the same visual grammar below.
- Topics: odd facts, medical/body, how everyday things work, animals, weird history — anything he "finds interesting", always as ONE strange question per video.

## The formula — every video, no exceptions

1. **One question.** The title is the curiosity itself plus ONE emoji at the end: "How A Hidden Bookshelf Door Works 🤔", "Why Ducks Sleep With One Eye Open 🤨", "Turning Your Finger Into A Gun 😨". If the topic needs context to sound interesting, it is not a topic.
2. **No intro, no title card.** The first frame is a scene already in motion — a character mid-problem. Nothing branded, nothing announced.
3. **The explanation IS a mini-story.** A character needs something → uses or discovers the thing → the mechanism is revealed step by step → the payoff reveal lands on the final frame. Facts ride on the story, never the other way round.
4. **Length 27–40 seconds.** Narration ~60–80 words as ONE continuous flow: sentences run across shots, no pauses, no greeting, no "part 2", no call to action.
5. **Ending = the reveal.** The last frame holds the payoff (the hidden room, the result, the twist). No outro. The stillness of the final frame against the motion before it is what makes people loop and comment.

## Visual grammar (from the frame-by-frame breakdown)

- **Locked recurring characters.** His current run uses the same girl (double buns, pink tank top) plus a tiny sidekick creature with giant ears across videos. Lock Zeesh's character sheet the same way and reuse it — recognition is the brand.
- **The camera ladder, always moving:** wide establishing → medium → close-up of the hands/action → MACRO of the mechanism → cutaway/X-ray of the internals → flat schematic/diagram view → back to wide for the payoff. Never two similar shots in a row; a cut or camera move every 1–2 seconds.
- **Cutaways are the signature.** The invisible is made visible: circuit boards, relay coils, magnetic locks, inside the body. If the narration names a hidden part, the picture must show that part at that second.
- **Highlight graphics.** Neon-green arrows, outlines and diamond markers appear on the exact part being explained; animated light pulses travel along wires and paths to show signals/energy moving.
- **In-scene branding.** His name is printed on the circuit-board chip inside the scene (18s of the reference video). For Zeesh this is the WhoaWire tag rule: the brand on a natural object inside the scene, placement varying per video — never an overlay logo.
- **Palette.** Bright, saturated environments (cyan/teal walls, warm wood, colorful props). The payoff space flips to dark + neon for contrast.
- **Real-feeling props.** Fake but readable in-world details (book covers with proper titles and cover art) sell the world. Never leave a prop blank or gibberish when the camera gets close.
- **Transitions.** Whip/motion-blur cuts into mechanism beats. No fades, no black frames except a deliberate inside-the-mechanism beat.

## Captions

- Bold white text with a black outline, bottom-center of the 9:16 frame.
- 2–4 word chunks, phrase by phrase, exactly synced to the narration — the caption stream is the narration itself, broken mid-sentence across shots ("As you pull / the book forward / it tilts / on a tiny hinge…").
- No emojis in captions, no punctuation piles, no on-screen title text. The title lives only in the YouTube title field.

## Narration and sound

- Calm, dramatic male narrator, even pace (~2–2.5 words per second), zero filler. Every sentence adds a new fact or the next step of the mechanism.
- Script shape: situation hook (often visual before the first word) → a cause-and-effect chain ("as you pull X, it tilts on Y, triggering Z…") where each step causes the next → one reveal line at the end.
- Sound bed is never empty: soft background music under everything, small emphasis sounds on mechanism beats.

## Topic selection

- Ask: "Would a stranger stop scrolling for this question?" Proven veins: your body ("What happens if…", how a body process works), everyday mechanisms (locks, doors, toilets, stitches, anchors), animals behaving strangely, weird-but-true history with a visual twist, "why" questions about ordinary things.
- One video = one question = one mechanism. Never two facts in one short.

## Production route for Zeesh (zero budget)

1. Script first: 60–80 words, one flow, cause→effect chain, reveal line last.
2. Shot list from the camera ladder: 8–12 shots, each a different size/angle from the last.
3. Generate clips per shot with the locked character sheet as reference (image-to-video); keep the character's clothes, hair and sidekick identical in every shot.
4. Assemble vertical 9:16, master 1080x1920. Captions chunked 2–4 words, bottom-center, white + black outline.
5. Narration via `/opt/hatch/bin/tts` (Casper, `avocado_v2:casper`) — write flowing comma-joined sentences, not fragments.
6. Verify the finished video with the `generated_video_verification` skill before delivering it.
7. Brand split (owner rule, never cross): science / how-it-works = **WhoaWire**; crime / dark history = **fume**. WhoaWire YouTube was removed in Oct 2026 — WhoaWire lives on TikTok/Instagram unless Zeesh decides otherwise.

## QA checklist — fail the video if any answer is no

- Is the first frame already a scene in motion (no intro/title card)?
- Does every shot differ from the previous one in size or angle?
- Is the hidden mechanism SHOWN in a cutaway, not just described?
- Do highlight graphics point at the exact part the narration names?
- Are captions 2–4 word chunks, synced, bottom-center?
- Does it end on the reveal with no CTA or outro?
- Is it one question only, 27–40 seconds?
