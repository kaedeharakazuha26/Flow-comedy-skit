# Google Flow Director

A directing and prompt-engineering skill for turning comedy skit scripts into continuity-locked, production-ready **Google Flow** video packs (`Frames-to-Video`, `Ingredients-to-Video`, or `Extend`).

## What This Skill Does

- **Interactive 7-Point Director's Checklist (Hard Gate):** Inspects your script, character reference photos, and optional reference video first, pre-fills known details, and confirms Flow mode, aspect ratio (`9:16` or `16:9`), setting/time of day, lighting style, camera and two-person framing, emotional intensity, wardrobe mode (`A` custom, `B` mirror reference photos, or `C` omit), and pacing before generating prompts. Supports per-item `auto` or `all auto` shortcuts.
- **2-Person Visible 9:16 Blocking & Speaker-Lock:** Keeps both characters clearly visible in vertical framing using three proven setups—**Stacked Depth (Foreground/Background)**, **Tight Side-by-Side Seated (3/4)**, and **Dirty Over-the-Shoulder (OTS)**—paired with a mandatory **Silent-Listener Lock** and a one-speaker-per-clip rule so Google Flow does not animate the wrong character's mouth.
- **4-Tier Emotion & Vocal Energy Ladder:** Maps performance intensity across four tiers (**Tier 1 Deadpan**, **Tier 2 Expressive Banter / Smug**, **Tier 3 Silent Shock / Jaw-Drop Freeze**, and **Tier 4 Explosive Shout / Panic**). Pairs coiled physical tension in Start Frames with body-impulse, facial-muscle, and vocal-projection cues plus tier-matched natural audio footers so shouting beats stay loud and energetic instead of flat.
- **Face, Wardrobe & Room Continuity:** Uses a **Master Start Frame 1** workflow to lock environment and lighting across cuts, enforces 180-degree blocking and eye-line math, neutralizes smiling or prop-holding reference photos into closed-mouth Start Frames, keeps wardrobe details out of video prompts to avoid face drift, and enforces positive-only Flow phrasing (zero negative triggers, genre buzzwords, or unintended background music).
- **Dialogue Pacing & Pronunciation Guardrails:** Enforces clip word budgets (`~8–15 words` for `3–4s` clips, `~16–22 words` for `5–6s`), spoken-form formatting for numbers and currency, and natural speech cadence cues for English, Tagalog, and Taglish scripts.
- **Edit-Ready CapCut Post-Production Notes:** Specifies exact trim beats (`cut 0.2s after last word` vs. `hold 1.0s silent shock`), offloads snap-zooms, freeze-frames, and screen text overlays to CapCut to protect facial likeness, and marks SFX and viral reaction meme-splice slots.
- **Surgical Fix-It Mode:** Bypasses the 7-point checklist when you return mid-production with a flawed render (flat shouting, wrong mouth moving, unintended smiling, rushed speech, or face drift) and outputs only the patched Shot and Start Frame.

## Output Structure

For every new script, the skill generates a complete production pack in four parts:

1. **Scene, Cinema & Continuity Lock** — Format, Flow mode, location, lighting plan, camera and two-person blocking plan, 180-degree eye-lines, locked wardrobe details, and `@Character` handles.
2. **Part 1: Shot-by-Shot Breakdown & Video Prompts** — Per-shot duration, framing, lighting, emotion tier, verbatim dialogue, CapCut edit cues, and a copy-paste 2–4 sentence `plaintext` video prompt.
3. **Part 2: Paired Start Frame Still-Image Prompts** — Master Start Frame 1 anchor instructions followed by still-image prompts for each shot (or shared-angle reuse notes with 1-line expression swaps to save credits).
4. **Part 3: Quick Pairing Table & Render Checklist** — A shot-to-Start-Frame mapping table plus three credit-saving render checks.

## Repository Structure

```text
.
├── README.md
└── google-flow-director/
    └── SKILL.md
```

## Quick Usage

1. Load [`google-flow-director/SKILL.md`](google-flow-director/SKILL.md) in your AI agent or copy its workflow into your skill directory.
2. Paste your comedy script (optionally attaching character reference photos or a reference video).
3. Answer the 7-point Director's Checklist (or reply `all auto` to let the skill choose per shot).
4. Generate **Start Frame 1** first in Google Flow, attach it alongside character references for **Start Frames 2–N**, then render each shot in **Frames-to-Video**.
5. If a single rendered clip misses the mark, describe the issue (e.g., *"Shot 3 shouting is too flat"* or *"the listener's mouth moved in Shot 2"*) to trigger **Surgical Fix-It Mode**.
