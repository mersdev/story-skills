---
name: story-to-video-storyboard
description: Write text-only 12-frame story plans, profiles for up to three named speaking characters, and three four-panel Google Flow storyboard prompts. Never generate media or require character images.
---

# Story-to-Video Storyboard

## Text-only rule for every step

The assistant writes and revises text only. In Steps 0–3, never generate, edit, render, preview, upload, or delegate the creation of images, audio, animation, or video. Never call a media tool or send a prompt to Google Flow. The final Google Flow prompts are text for the user to copy; their instructions are not actions for this assistant. Do not require the user to create or upload media to advance. If the user already supplied an image, it may be inspected read-only as an optional reference, but every step must work from text alone.

## Story contract

- Plan exactly **12** chronological frames, each an individual **16:9 landscape video scene**. Deliver three standalone four-panel text prompts for global Frames 1–4, 5–8, and 9–12, one prompt per reply. Wait for `Next` between prompts.
- Create **one to three characters total** for the story. Each created character must have a **distinct proper name** and at least one **6–7-word spoken line** in the approved 12-frame plan and final scripts. Count any named voice-over presenter in this limit. A role label such as `Narrator`, `Soldier`, or `Parent` is not a character name. Do not create profiles or individual appearance prompts for silent people, animals, crowds, or unnamed extras. Silent background participants may appear only as incidental context, not as additional designed characters.
- Every spoken line, including voice-over, has exactly **6 or 7 spoken words**, excluding the speaker's name. A silent frame uses `Dialogue: None (silent panel)`. Preserve protected historical quotations; if their word count conflicts, ask to adapt or depict the quotation as an action instead of changing it.
- Give each created character **Prompt A**, a text-only appearance description for one person on a plain neutral background, and **Prompt B**, one paragraph of exactly **100 words** on personality and speaking behavior. These are written descriptions; producing character images is outside this workflow.
- Keep historical facts distinct from reenactment choices. Do not present invented dialogue or visual staging as documented fact. Use a named fictional present-day presenter for voice-over when attributing invented narration to a historical person would mislead.
- In final panel `Description:` fields, use character names, dialogue, acting, poses, and actions without restating their appearance or wardrobe. Put the approved design and detailed location continuity in `STYLE CONSISTENCY:`.

## Workflow

| Step | Output | Continue when |
|---|---|---|
| 0. Brief | Ask for missing story, style, setting, audience, language, and essential facts or dialogue | User answers or accepts defaults |
| 1. Plan | Show all 12 frames in three groups of four | User approves the plan |
| 2. Characters | Give Prompt A and Prompt B for each of the 1–3 named speakers | User approves the written designs |
| 3. Storyboards | Give exactly one four-panel Markdown text block per reply | `Next` advances to the next block |

Track internally: approved facts and style; locations and their fixed physical anchors; each frame's cast and dialogue; the 1–3-character speaking roster and designs; current step and next frame group. Recheck the cast and dialogue after every revision. If a proposed change adds a fourth designed character or leaves one without a spoken line, revise the plan before continuing.

### Step 0 — Brief

Ask only for details not already supplied: story and facts; visual style; **one to three named speaking characters**; time and place; audience, language and tone; any protected dialogue or constraints. Explain that the output will remain text-only, including character descriptions and final storyboard prompts. Offer sensible defaults for optional preferences. Wait for the user's reply before writing frames.

### Step 1 — Review all 12 frames

Show `Frames 1–4`, `Frames 5–8`, and `Frames 9–12`. For each frame include `Frame N — Title`, `Action:`, `Shot:`, `Characters:`, `Dialogue:`, `Environment:`, and relevant `Continuity:`. `Characters:` names the created speaking cast present or heard in that frame; incidental background participants need no profile. Ensure every created character speaks at least once somewhere in the 12 frames.

Build a consistent world description for each recurring location: architecture, layout, entrances, landmarks, permanent props, light direction, time, weather, and camera geography. Distinguish different locations and mark historical reconstructions as such. Ask for changes or approval, then stop.

### Step 2 — Named speaking characters

For each approved speaker, in roster order, write:

1. **Character information:** proper name, role, dialogue frame numbers, approved or reference-grounded appearance, personality, voice, and any uncertain reconstructed detail.
2. **Prompt A — Appearance (text only):** one character, face, hair, build, clothing, colors, accessories, posture, and a plain neutral background. No other character or scene. This is a written design, not a request to make an image.
3. **Prompt B — Acting and speaking (text only):** exactly 100 words in one paragraph covering temperament, delivery, pace, emphasis, gestures, reactions, and the character's speaking role.

Ask for revisions or approval. After approval, proceed directly to Step 3; no image-generation or upload checkpoint.

### Step 3 — One four-panel storyboard prompt per reply

On initial Step 2 approval, output global Frames 1–4. On the first `Next`, output Frames 5–8. On the second `Next`, output Frames 9–12. Then finish. Each reply contains exactly one fenced `text` block; its first line is exactly `Create a storyboard based on the panels below:`. Use local labels `Panel 1`–`Panel 4` and fill every field with story-specific text:

```text
Create a storyboard based on the panels below:

Panel 1: {Title}
Dialogue: {Proper name}: “{6 or 7 spoken words}”
Description: {Individual 16:9 landscape video scene, action, camera, and detailed environment.}

Panel 2: {Title}
Dialogue: {Proper name}: “{6 or 7 spoken words}”
Description: {Distinct scene and consistent environment.}

Panel 3: {Title}
Dialogue: {Proper name}: “{6 or 7 spoken words}”
Description: {Distinct scene and consistent environment.}

Panel 4: {Title}
Dialogue: {Proper name}: “{6 or 7 spoken words}”
Description: {Distinct scene and consistent environment.}

STYLE CONSISTENCY:
VISUAL STYLE & VIDEO: {Approved style; four separate 16:9 landscape video scenes.}
ENVIRONMENT LOCK: {Full layout, landmarks, materials, props, light, time, and weather for every location shown; repeat across independent prompts.}
CHARACTER DESIGN LOCK: {Only the approved named speaking characters appearing or heard here; repeat each relevant approved text design and keep identities distinct.}
```

Use `Dialogue: None (silent panel)` for any approved silent frame. A speaker may be heard in voice-over without appearing on screen; label that clearly. Do not invent a reference image, Flow handle, or extra character. After the first or second block, ask for `Next` in plain text. After the third, say the three written scripts are complete.

## Revisions and final check

Update affected frames, dialogue, character designs, and location locks together. If a change makes a designed character silent or raises the created cast above three, correct it before delivering another block. Before every reply, verify text-only output, exactly 12 planned frames, 1–3 properly named characters each with dialogue, 6–7 words per spoken line, the 100-word Prompt B rule, and one four-panel block per Step 3 reply.
