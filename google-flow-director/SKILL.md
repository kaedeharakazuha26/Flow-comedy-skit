---
name: google-flow-director
description: Use when the user pastes a comedy skit, dialogue scene, or video script for Google Flow (Frames to Video, Ingredients to Video, or Extend), wants interactive filming direction (lighting, camera angles, 2-person visible 9:16 blocking via stacked depth, side-by-side, or dirty OTS, 4-tier emotional/shouting vocal intensity, Tagalog/Taglish pacing, wardrobe), needs face-consistent Start Frames without unintended smiling or face drift, or needs surgical single-shot Fix-It retries.
---

# Google Flow Director

Turn any comedy script into a complete, continuity-locked Google Flow production pack with cinema-grade lighting, 2-person visible 9:16 blocking, high-energy vocal delivery, Start Frames, and edit-ready CapCut cues.

## Hard Gate: Ask the Filming Checklist First

When the user pastes a new script without specifying every filming decision (and without explicitly writing `"skip questions"` or `"all auto"`), **STOP and ask the One-Shot Director's Checklist before generating any prompts.**

**Violating the letter of this gate violates its spirit.** Even if the user says "I'm in a rush" or "make it fast," generate ZERO Start Frame prompts and ZERO video prompts until they answer the checklist or explicitly delegate choices with `auto`.

**Surgical Fix-It Exception:** If the user is returning mid-production to repair 1–2 rendered shots (weak/malamya shout, wrong character's mouth moving, face drift, unintended laugh, mispronounced Tagalog), skip the checklist and jump straight to `## Surgical Fix-It Mode`.

## Step 1: Inspect Inputs & Ask the One-Shot Director's Checklist

Before replying, inspect everything the user gave you:
- **Script:** Extract speakers, beat count, setting/time clues, required props, wardrobe clues, and spoken language.
- **Character reference photos (if attached):** Note exact garment cut, color, texture, collar/sleeves, and accessories. Flag any wide smiles or unintended held props (cups, phones) that must be neutralized in Start Frames.
- **Reference video (if attached):** Note camera placement, left/right blocking, shot durations, lighting, and emotional progression to mirror.

In your first reply:
1. **Pre-fill what the script already answers** in a short editable summary (characters, setting/time clues, script props, wardrobe clues, spoken language) so the user never repeats themselves.
2. **Present the numbered 7-point Director's Checklist.** Tell the user they can reply in one message, write `auto` on any single item to let you decide shot-by-shot, or reply `all auto`:
   1. **Flow Mode & Aspect Ratio:** `Frames-to-Video` (recommended default for multi-cut continuity), `Ingredients-to-Video`, or `Extend` (single continuous angle only); `9:16` vertical or `16:9` horizontal.
   2. **Place / Location & Time of Day:** Confirm or adjust setting, time of day, and key background landmarks.
   3. **Lighting Style:** Pick one or mix per shot (`auto per shot`): `High-Key`, `Low-Key`, `Rembrandt`, `Butterfly`, `Underlight`, `Silhouette`, `Neon`, or `Natural`.
   4. **Camera Angles, 2-Person Framing & Movement:** Pick one, mix per beat, or `auto per shot`: 2-person visible 9:16 setups (`Stacked Depth FG/BG`, `Tight Side-by-Side Seated 3/4`, `Dirty OTS`) or `Classic Solo Cuts`, plus angles/moves (`Static Eye-Level` safest default, `Extreme Wide`, `Low Angle`, `High Angle`, `Dutch Angle`, `Bird's Eye View`, `POV`, `Dolly Zoom`).
   5. **Emotions, Vocal Intensity & Delivery:** Pick overall arc or per-beat level using the 4-Tier Emotion & Vocal Energy Ladder (`Tier 1 Deadpan`, `Tier 2 Expressive Banter/Smug`, `Tier 3 Silent Shock/Freeze`, `Tier 4 Explosive Shout/Panic`), spoken language (`Tagalog`/`Taglish`/`English`), and directing-notes language (natural Taglish for Filipino scripts, otherwise match user).
   6. **Wardrobe Handling:**
      - **(A) Custom wardrobe:** User specifies outfits (locked verbatim in Start Frames, omitted from video prompts).
      - **(B) Follow character reference:** Mirror uploaded photos consistently in Start Frames without inventing logos or props (omitted from video prompts).
      - **(C) Omit wardrobe:** No wardrobe descriptions in Start Frames or video prompts.
   7. **Characters, Pacing & Post-Edit:** Confirm `@Character` handles, target runtime/clip pace (default `1.5s–4.5s` per cut; word budget `~8–15 words` for `3–4s` or `~16–22 words` for `5–6s`), and CapCut edit cues (trim beats, snap-zoom/freeze-frame offload, SFX, and viral meme-splice slots).
3. **End the turn** and wait for the user's reply.

## Cinematography Quick Reference

### Lighting Styles (Lock in Master Start Frame 1 & Repeat Across Cuts)

| Style | Visual Setup | Mood / Best For | Flow Prompt Cue |
| :--- | :--- | :--- | :--- |
| **High-Key** | Bright even illumination, minimal shadows | Cheerful, upbeat, commercial, light comedy | `bright, even high-key lighting` |
| **Low-Key** | Dark surroundings, half-lit face, deep shadow | Mystery, suspense, noir, serious tension | `dark low-key lighting, half-lit face` |
| **Rembrandt** | Angled side key casting a light triangle on cheek | Classic drama, heavy emotional weight | `dramatic Rembrandt side lighting` |
| **Butterfly** | Front overhead key, tiny shadow under nose | Flattering portrait, beauty, hero shot | `soft overhead butterfly lighting` |
| **Underlight** | Harsh upward light from below the chin | Instant horror, eerie, sinister beat | `harsh upward underlight from below` |
| **Silhouette** | Strong bright backlight, dark foreground figure | Dramatic reveal, anonymity, iconic entrance | `strong backlight silhouette, dark subject` |
| **Neon** | Dual colored rim lights (e.g., red and blue) | Stylized mood, nightlife, heightened emotion | `red and blue neon rim lighting` |
| **Natural** | Morning/afternoon daylight or warm practical light | Realistic everyday skits, slice-of-life | `natural daylight` / `warm indoor light` |

### Camera Angles & Movement

| Angle / Move | Framing & Motion | Emotional Effect | Google Flow Guardrail |
| :--- | :--- | :--- | :--- |
| **Static Eye-Level** | Locked tripod frame at eye height | Neutral, natural dialogue | Safest default; always write `static` to prevent drift |
| **Extreme Wide** | Distant view showing full place and spacing | Establishes location, scale, distance | Ideal for Master Start Frame 1 |
| **Low Angle** | Camera low looking upward at subject | Dominant, intimidating, powerful | Lock upward gaze and stature in Start Frame |
| **High Angle** | Camera high looking downward at subject | Vulnerable, pressured, underdog | Lock downward tilt and upward eye-line in Start Frame |
| **Dutch Angle** | Visibly tilted horizon framing | Unease, standoff, off-balance tension | Keep `static` on the tilt; do not combine with pans |
| **Bird's Eye View** | Directly overhead top-down view or tracking | Chase, race, urgency, spatial clarity | One steady overhead tracking motion only; no mid-clip cuts |
| **POV** | First-person lens as a character's eyes | Immersion, puts viewer inside confrontation | Direct eye contact into lens; lock foreground props in Start Frame |
| **Dolly Zoom** | Background warps/compresses, subject stays same size | Sudden shock, dread, plot-twist realization | Isolate to its own 2s to 3.5s single-beat reaction clip |

### 2-Person Visible 9:16 Blocking & Speaker-Lock

| Setup | 9:16 Spatial Placement | Best Comedy Use |
| :--- | :--- | :--- |
| **Stacked Depth Two-Shot (FG / BG)** | Person A lower-right foreground (seated/reclined); Person B upper-left background (standing behind sofa/doorway). | Keeps both faces large in vertical frame for continuous prank/setup beats without shrinking faces. |
| **Tight Side-by-Side Seated (3/4)** | Both seated closely on sofa or table, angled slightly inward toward each other. | Plays simultaneous shout/scolding + stifled laugh/smirk in one continuous cut. |
| **Dirty Over-the-Shoulder (OTS)** | Speaker fills ~60% frame in crisp MCU; listener's out-of-focus shoulder/back-3/4 anchors the foreground edge. | Ideal for sharp micro-expression callouts and sudden jaw-drop shock cuts. |

- **Silent-Listener Lock:** Whenever two faces are visible, explicitly describe the non-speaking character's closed mouth and silent physical reaction (e.g., `while @Husband on the right stays completely silent with a tight closed-mouth smirk, glancing at his phone`) so Flow does not animate the wrong mouth.
- **One Speaker per Clip:** Default to 1 speaker per `3–5s` clip (max 1 brief volley only when turn-taking is anchored to an unmistakable physical cue).
- **4th-Wall Deadpan Glance (Optional Comedy Beat):** Character breaks eye-line to look directly into the lens with flat brows and closed mouth before cutting.

### 4-Tier Emotion & Vocal Energy Ladder

| Tier | Start Frame Prep | Video Prompt 3-Layer Stack (Body + Face + Voice) | Matched Audio Footer |
| :--- | :--- | :--- | :--- |
| **Tier 1: Deadpan / Understated** | Relaxed closed-mouth flat face, neutral posture | Flat gaze, slow blink, steady posture; `flat, matter-of-fact [Language] voice` | `Raw natural indoor voice, ambient room tone.` (or outdoor equivalent) |
| **Tier 2: Expressive Banter / Smug** | Slight lean-in, raised brow or closed-mouth half-smirk | Crisp brow lifts, side-eye, rhythmic head tilts; `sharp, animated, conversational [Language] voice` | `Clear natural indoor voice, ambient room tone.` |
| **Tier 3: Silent Shock / Jaw-Drop Freeze** | Pre-freeze closed mouth (or slightly parted for instant gasp) | Spine snaps upright, horizontal forehead creases, eyes pop wide exposing upper sclera, jaw drops into a silent frozen "O" | `Quiet indoor room tone.` |
| **Tier 4: Explosive Shout / Panic** | **Coiled physical tension:** closed mouth, forward lean, deep vertical furrow between brows, flared nostrils, tense jaw/neck, hand poised to point/slam | **Kinetic body impulse** (whips head 90 degrees, leans in sharply, jabs accusing finger downward, slams table) + **facial anatomy** (wide-open shouting mouth showing upper and lower teeth, strained neck) + **vocal force** (`yelling loudly at the top of her lungs in a sharp, explosive, high-volume [Language] voice`) | `Loud, projecting raw indoor voice with natural room echo, crisp vocal acoustics.` (**Never** use `quiet` on Tier 4) |

## Step 2: Continuity Locks & Prompt Formulas

### Mandatory Continuity Rules
- **Consistent `@Character` handles:** Use exact `@Name` tags everywhere (e.g., `@Wife`, `@Husband`, `@Mina`, `@Jun`).
- **Master Start Frame 1 Workflow (Frames-to-Video):** Instruct the user to generate **Start Frame 1 (widest/establishing master)** first using character reference photos, then attach Start Frame 1 as the environment and lighting anchor alongside character photos for Start Frames 2 to N.
- **180-Degree Blocking & Eye-Line Math:** Lock left/right screen placement and matching look directions across all cuts (if Character A is on the left looking right/down-right, Character B is on the right looking left/up-left). Never flip sides unless a character physically moves across frame.
- **Closed-Mouth Start Frames & Tier 4 Coiled Tension:** Always specify closed-mouth neutral, stern, annoyed, tired, or smug expressions for non-smiling lines (slightly parted only for instant shock/gasp). Explicitly neutralize smiling or prop-holding reference photos inside Start Frames, keep hands empty unless a script prop is required, and avoid invented logos or text. **For Tier 4 Shouts, never start from a relaxed neutral posture:** pre-load forward lean, deep brow furrow, flared nostrils, tense jaw/neck, and poised hand posture in the Start Frame.
- **Tagalog/Taglish Word Budget & Speech Formatting:** Keep spoken lines within `~8–15 words` for `3–4s` clips (`~16–22 words` for `5–6s`) so punchlines never rush or clip mid-word. Spell out numbers, currency, and tricky acronyms cleanly inside quotes (`limang daan` / `five hundred` instead of `500`, `G-Cash` if misread) and include `natural conversational Filipino cadence` on Tagalog/Taglish lines to avoid American accent drift.
- **Wardrobe Mode Execution:** Mode A (Custom): repeat the full concrete wardrobe phrase in every Start Frame (never write "same clothes"); omit from video prompts. Mode B (Follow Reference): describe visible garments cleanly from uploaded photos inside Start Frames only, removing unwanted props/smiles; omit from video prompts. Mode C (Omit): zero wardrobe details anywhere.
- **Separate Cuts vs. Extend:** Default to separate Frames-to-Video clips per shot. Never recommend Extend for alternating solo close-ups (Extend morphs or invents off-camera faces). Use Extend only if the user explicitly chose one continuous static angle.

### Video Prompt Formula (2 to 4 Sentences per Clip)

Build every `plaintext` video prompt with these exact four parts in order:
1. **Framing, Eye-Line & Lighting Lock:** `[Aspect ratio] [static or single move] [camera angle, 2-person setup & shot size] of [@Character(s)] [screen side & eye-line], [brief location & lighting cue].`
2. **Concrete Physical Performance & Silent-Listener Lock:** Describe visible body impulse and facial muscle cues using the 4-Tier 3-Layer Stack, and on every 2-person visible shot explicitly lock the non-speaker's closed mouth and silent reaction.
3. **Spoken Dialogue (omit on silent beats):** `Speaking/Yelling in a [tier-matched vocal energy] [Spoken Language] voice with natural conversational Filipino cadence, [@Character] says/yells: "[Exact verbatim line]"` (use `!` naturally on Tier 4 shouts).
4. **Matched Natural Audio Footer:** Select the exact audio footer matching the shot's Emotion Tier from the 4-Tier Ladder (reserving `quiet` strictly for Tier 3 silent/whisper beats, and using `Loud, projecting raw indoor voice with natural room echo, crisp vocal acoustics.` for Tier 4 shouts).

### Zero-Tolerance Banned Elements Inside Video Prompts
- **No negative phrasing:** Never write `no smiling`, `no laughing`, `no background music`, `no BGM`, `do not`, or `don't`. Video tokenizers trigger the forbidden concept. State positive visuals instead (`calm, completely neutral face with a relaxed mouth`).
- **No `quiet` on loud/shouting shots:** `quiet room tone` dampens vocal energy and causes flat/malamya delivery.
- **No unlocked second character in 2-person shots:** Always state the listener's silent closed-mouth reaction.
- **No genre or meta triggers:** Omit `comedic`, `comedy`, `sitcom`, `funny`, `strict 1:1 facial consistency`, and `--ar 9:16`.
- **No SFX, music cues, or Flow-generated post-FX:** Keep framing clean/static in Flow; offload snap-zooms, B&W freeze-frames, readable phone-screen text, SFX, and viral meme splices to CapCut.
- **No long wardrobe/room walls of text, double moods, double camera moves, or > 2 rapid dialogue lines** crammed into one 3s clip.

### Start Frame Still-Image Prompt Formula (Frames-to-Video)

1. `[Aspect ratio] [vertical/horizontal] [camera angle & shot size] photograph of [@Character(s)] [FG/BG or side-by-side placement & setting].`
2. `[Wardrobe lock per Mode A or Mode B; omit completely in Mode C.]`
3. `[Exact opening pose (coiled physical tension for Tier 4 shouts), empty hands or required script prop, eye-line direction, closed-mouth opening expression.]`
4. `[Matching background landmarks from Start Frame 1.]`
5. `[Chosen lighting style cue], shallow depth of field, realistic skin texture.`

Never put dialogue or multi-step motion verbs inside Start Frames. Whenever two or more shots share identical framing, combine them under one Start Frame heading and add a 1-line expression-swap bullet (`Para sa Shot [N] ([Mood]): Palitan lang ang expression line sa itaas ng: [replacement].` or English equivalent).

## Step 3: Required Output Structure

Deliver the finished pack in this exact order:
1. **Scene, Cinema & Continuity Lock:** Aspect Ratio, Flow Mode, Location & Time, Lighting Plan, Camera & 2-Person Blocking Plan, 180-Degree Eye-Lines, Wardrobe Mode & Lock, `@Character` Handles.
2. **Part 1: Shot-by-Shot Breakdown & Video Prompts:** Per shot (`### Shot [N] - [Duration]s | [Camera Angle & Shot Size] ([Beat Label])`), list `Camera & Lighting`, `Emosyon & Action` (with Tier), `Dialogue (@Character)`, optional `Post-Edit SFX / Cut (CapCut)` (exact trim beat like `cut 0.2s after last word` vs `hold 1.0s silent shock`, snap-zoom/freeze-frame offload, SFX, and meme-splice slot), and a `plaintext` 2 to 4 sentence video prompt.
3. **Part 2: Paired Start Frame Still-Image Prompts:** For `Frames-to-Video`, open with the Master Start Frame 1 anchor instruction, then list every Start Frame in `plaintext` code blocks with credit-saving reuse notes. For `Ingredients-to-Video`, omit the full Start Frame batch and include still-frame prompts only where a neutral facial reset or custom setup is needed.
4. **Part 3: Quick Pairing Table & Render Checklist:** Markdown table (`Shot | Start Frame | Framing, Lighting & Tier | Dialogue Cue | Target Cut & Edit Note`) plus 3 concise credit-saving render checks.

## Worked Mini-Example

### Shot 3 - 4.0s | Tight Side-by-Side Seated Two-Shot (Tier 4 Explosive Shout + Silent-Listener Lock)
- **Camera & Lighting:** Static eye-level tight side-by-side seated two-shot (`@Wife` left, `@Husband` right) in warm natural living-room light.
- **Emosyon & Action (Tier 4):** Coiled frustration explodes—`@Wife` whips her head 90 degrees right, leans in sharply, jabs an accusing finger downward, and yells while `@Husband` suppresses a smug smirk.
- **Dialogue (`@Wife`):** "Naglinis ako nang buong bahay tapos hindi pala tuloy?!"
- **Post-Edit SFX / Cut (CapCut):** Hard cut `0.2s` after `"tuloy?!"`; add optional 112% CapCut snap-zoom on `"buong bahay"`.

```plaintext
9:16 static eye-level tight side-by-side medium two-shot of @Wife seated on the left and @Husband lounging on the right of a beige sofa in a warm sunlit living room. @Wife abruptly whips her head ninety degrees right toward @Husband, leans in sharply, jabs her index finger downward, and opens her mouth wide showing upper and lower teeth with strained neck muscles while @Husband stays completely silent with a tight closed-mouth suppressed smirk looking down at his smartphone. Yelling loudly at the top of her lungs in a sharp, explosive, high-volume Tagalog voice with natural conversational Filipino cadence, @Wife yells: "Naglinis ako nang buong bahay tapos hindi pala tuloy?!" Loud, projecting raw indoor voice with natural room echo, crisp vocal acoustics.
```

### Shot 4 - 2.0s | Dirty OTS Tight MCU on `@Husband` (Tier 3 Silent Jaw-Drop Shock + Meme Splice)
- **Camera & Lighting:** Static eye-level Dirty OTS MCU on `@Husband` centered-right, with blurred edge of `@Wife`'s shoulder and dark hair in lower-left foreground; warm natural living-room light.
- **Emosyon & Action (Tier 3):** Instant caught-red-handed freeze—eyebrows shoot maximally up, eyes snap wide, jaw drops into a silent "O".
- **Post-Edit SFX / Cut (CapCut):** Hold `1.0s` silent jaw-drop → hard cut to viral laughing reaction meme splice.

```plaintext
9:16 static eye-level over-the-shoulder tight medium close-up of @Husband centered-right on the beige sofa in a warm sunlit living room, with the softly blurred edge of @Wife's shoulder and dark hair anchoring the lower-left foreground. Caught off guard, @Husband stiffens his posture upright as his eyebrows shoot maximally upward creating horizontal forehead creases, his eyes snap wide open exposing upper sclera, and his jaw drops vertically into a frozen silent open mouth staring left toward @Wife. Quiet indoor room tone.
```

### Start Frame 3 - Tight Side-by-Side Seated Two-Shot (Coiled Tier 4 Prep for Shot 3)
```plaintext
9:16 vertical eye-level tight side-by-side medium two-shot photograph of @Wife seated upright on the left and @Husband lounging on the right of a beige sofa in a warm sunlit living room. @Wife wears a plain gray cotton crewneck t-shirt and dark shorts; @Husband wears a white ribbed tank top and dark joggers, holding a smartphone in his left hand. @Wife is coiled with tension, leaning slightly forward with deep vertical furrows between her brows, flared nostrils, tense jaw and neck, right hand poised near her lap, and a tight closed-mouth scowl angled toward @Husband, while @Husband lounges casually looking down at his phone with a smug closed-mouth half-smirk. Softly blurred cream curtains and potted plant behind the sofa. Warm natural indoor lighting, shallow depth of field, realistic skin texture.
```

## Surgical Fix-It Mode (Mid-Production Retries)

When the user reports a flawed rendered clip from an existing pack, **bypass the 7-point checklist** and return ONLY the patched Shot + Start Frame (if a Start Frame tweak is needed):

| Reported Symptom | Likely Cause | Surgical Fix |
| :--- | :--- | :--- |
| **Flat / "malamya" shouting** | Relaxed Start Frame, vague `shouts:`, or `quiet room tone` footer | Upgrade Start Frame to Tier 4 coiled tension + add kinetic body impulse + wide-open shouting mouth/strained neck + switch footer to `Loud, projecting raw indoor voice with natural room echo, crisp vocal acoustics.` |
| **Wrong character's mouth moves (2-person shot)** | Listener left undescribed or 2 speakers packed in 1 clip | Enforce 1 speaker per clip and add explicit Silent-Listener Lock (`stays completely silent with a tight closed-mouth [reaction]`). |
| **Unintended smiling or laughing** | Smiling reference photo or negative words (`no smiling`) | Regenerate closed-mouth stern/coiled Start Frame; swap any negations for positive muscle cues. |
| **Rushed, cut-off, or mispronounced Tagalog** | Over word budget or raw numbers/acronyms in quotes | Trim or split across 2 cuts (`~8–15 words` per `3–4s`); spell out numbers/currency (`limang daan` / `five hundred`) + add `natural conversational Filipino cadence`. |
| **Face drift or warp mid-clip** | Long outfit/room details in video prompt or Flow camera zoom | Move outfit/room details strictly to Start Frame; lock `static` in Flow and apply snap-zoom in CapCut. |

## Red Flags & Rationalization Table

| Excuse | Reality |
| :--- | :--- |
| "User said they are in a rush, so I'll skip the checklist." | Skipping questions forces guessed lighting, angles, and outfits, wasting Flow credits. Always ask the checklist for new scripts unless user wrote `skip questions` or `all auto` (exception: Surgical Fix-It retries). |
| "Writing `no smiling` / `no BGM` makes the prompt clearer." | Video tokenizers attend to `smiling` and `BGM` and generate them. Describe positive facial muscles and matched natural audio instead. |
| "I'll end every video prompt with `quiet room tone` to stop BGM." | `quiet` dampens vocal loudness and ruins shouting scenes. Match the audio footer to the 4-Tier Emotion Ladder (`Loud, projecting...` for Tier 4). |
| "Both characters are visible so Flow will know who speaks." | Without a Silent-Listener Lock, Flow frequently animates both mouths or swaps speakers. Always lock the non-speaker's closed mouth and silent reaction. |
| "I'll repeat the outfit details inside the video prompt too." | Long wardrobe/room text competes with the reference image and causes face drift. Keep detailed wardrobe strictly in Start Frames. |
| "I'll use Extend between solo shots to keep the room." | Extend continues from the last frame and morphs faces across angle cuts. Default to separate Frames-to-Video clips per shot. |
| "The user's character photo is smiling, Flow will fix it." | Smiling start frames turn into laughter when speech begins. Neutralize to a closed-mouth Start Frame first. |
