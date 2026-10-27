---
name: story-skills
description: Create or update a self-contained, topic-locked classroom skill with a 12-frame plan, character prompts, and three paired storyboard-image and video prompts. Use when building a specialized skill, not when running one with students.
---

# Classroom Storyboard Skill Builder

This is the **authoring template**, not a student-facing lesson. Create or update a specialized `<topic>-storyboard-classroom/SKILL.md` for the requested story. The existing [Merdeka](merdeka-storyboard-classroom/SKILL.md), [Parameswara](parameswara-storyboard-classroom/SKILL.md), [Fall of Melaka](fall-of-melaka-storyboard-classroom/SKILL.md), and [Night Market Glitch](night-market-glitch-storyboard-classroom/SKILL.md) skills show the intended student experience. Use them as examples; do not copy their facts, fictional beats, character designs, or source claims into another topic.

The generated `SKILL.md` must work on its own. Include its complete topic, twelve locked beats, factual sources for historical claims or an explicit fiction declaration, character design, student commands, prompt formats, and checks. Do not make it depend on this template or another skill file at runtime. Preserve an existing specialized skill's approved topic and distinctive facts when editing it.

## Build the topic-specific skill

1. Use the teacher's story, audience, style, and cast when provided. Default to Malaysian primary and lower-secondary students, English for all non-dialogue text, and cinematic 3D family animation. At the first student step, ask whether **Dialogue** should be in English or Bahasa Melayu; do not choose for the student.
2. For history, research claims with authoritative sources and put direct links and the facts they support **inside the generated skill**. For original fiction, clearly identify the plot and world as fiction instead of inventing factual sources. Choose exactly twelve chronological, depictable beats that form one story: a central goal, rising obstacles, consequences, and a resolution. Keep legends, disputed details, and artistic reconstructions distinct from documented history. Include topic-specific visual safeguards such as period flags, buildings, clothing, and chronology where relevant. Do not invent precise dialogue, appearance, interiors, dates, or source-backed claims as historical facts.
3. Choose only the named main speaking characters the story needs; one lead plus an off-screen Narrator is the default in this repository. Every designed main character must speak in the plan. The Narrator needs no character image prompt; silent participants and crowds need no profile. Give each main speaker a fixed written design, while marking unsupported historical traits as reconstruction.
4. Write a unique lowercase hyphenated frontmatter `name` matching the skill folder and a description that names the fixed story and output. Make the lesson topic-locked: students may revise pacing, framing, or tone, but cannot switch its event or silently replace its twelve beats.
5. Write the student workflow and paired copy-ready prompt architecture below into the generated skill, replacing generic labels with the topic's beats and safeguards. Keep the generated file focused; add extra files only when the topic needs them.

## Rules every generated classroom skill must carry

### Text-only production contract

- The assistant writes prompts and may inspect user-uploaded images read-only. It never generates, edits, renders, previews, uploads, delegates, or sends image, audio, animation, or video media. The storyboard and video prompt commands are text for the student to copy, not instructions for the assistant to execute.
- Plan **twelve** chronological frames, grouped 1–4, 5–8, and 9–12. Each group becomes **one landscape 16:9 storyboard image** with four equal panels in a 2×2 grid and **one 16:9 video** with four sequential scenes.
- Deliver **two separate, standalone prompts per storyboard stage**: the four-panel image prompt first, then the matching four-scene video prompt. Use local `Panel 1`–`Panel 4` labels in each. Deliver only the current group per reply; never depend on preceding prompts.
- The dialogue-language choice changes **only spoken words inside `Dialogue:`**, including off-screen Narrator speech. It does not change the response or prompt language. Keep introductions, story and frame titles, headings, field labels, factual notes, scene descriptions, character prompts, style locks, and next-step instructions in English—even after the student chooses Bahasa Melayu. Never translate the fixed English title or labels such as `Historical fact:` and `Panel 1:`.
- Every non-silent `Dialogue:` line has **six or seven space-separated words** in the chosen English or Bahasa Melayu. Count spoken words, excluding the speaker label. A silent panel uses `Dialogue: None (silent panel)`. Preserve authentic quotations; if their wording conflicts with the count, describe the quotation as action and use a compliant Narrator line rather than altering it.
- Attribute invented historical speech to reenactment, not to a verified quotation. Respect the user's protected dialogue and the topic's historical boundaries.

### Student stages and approval gates

| Stage | Student action | Skill output |
|---|---|---|
| Welcome | Select skill or request `HELP` | Fixed topic; ask whether dialogue should be English or Bahasa Melayu |
| 1. Story plan | Choose dialogue language, or `START` after choosing | All twelve locked frames in three groups of four; ask for approval or revisions |
| 2. Character prompts | Approve plan or `NEXT` | Profile and two separate copy-ready text prompts for each main speaker; ask for approval or revisions |
| 2.5. Reference lock | Approve character prompts | Request final character image or `SKIP IMAGE`; inspect, reconcile, summarize, and ask for lock approval |
| 3. Storyboard I | Approve reference lock | Image and video prompts for global Frames 1–4 |
| 4. Storyboard II | `NEXT` | Image and video prompts for global Frames 5–8 |
| 5. Storyboard III | `NEXT` | Image and video prompts for global Frames 9–12; finish |

Recognize `START`, `NEXT`, `RETRY`, `HELP`, `SKIP IMAGE`, and the English/Malay language choice case-insensitively. Do not create the plan until the student chooses a dialogue language; if they type `START` or `NEXT` first, ask the language question and wait. Once chosen, proceed to Stage 1 without another command and remember the choice for every later `Dialogue:` field. `NEXT` otherwise advances only one stage and cannot skip the reference decision or approval gate. `RETRY` revises the current stage without changing the fixed topic. `HELP` briefly gives the current stage and one next action. Ask before restarting work already in progress. After the third storyboard, `NEXT` says the project is complete.

After a Bahasa Melayu choice, the Stage 1 reply must still begin in English, for example: `Dialogue language: Bahasa Melayu. Here is the 12-scene plan.` Continue with English prose and the exact English headings `Frames 1–4`, `Frame 1 —`, and `Historical fact:`; never translate them to `Kumpulan`, `Bingkai`, or `Fakta Sejarah`. Only the spoken text in `Dialogue:` may be Malay. Do not repeat or translate the welcome message.

In Stage 1, open with a short English `Story arc:` stating the protagonist's goal, what stands in the way, how the stakes rise, and where the story ends. Show each frame's historical anchor or fictional premise, depictable action, still-image composition, speaker or cast, dialogue or silence, environment, and `Continuity:`. For each frame, `Continuity:` must name what consequence or unresolved goal arrives from the previous frame and what change leads to the next; a shared costume or location alone is insufficient. Read all twelve frames in order and fix any jump that feels unrelated. When history does not support direct causation, connect beats through the protagonist's continuing goal or visible consequence without inventing a historical event. Keep a consistent internal world description for repeated locations: layout, fixed landmarks and props, light, weather, era when relevant, and camera geography. The twelve approved beats remain in order throughout the three prompt pairs.

In Stage 2, give each main speaker:

- **Character information:** role, dialogue frames, approved or reconstructed appearance, clothing, personality, and speaking style.
- **Prompt A:** one independently copyable `text` block for a single full-body character reference image on a clean studio background, with face, hair, build, clothing, colors, and accessories; no real person's name, exact likeness request, setting, other people, text, or watermark. Give the character's name and role outside the copyable block. This is a written prompt only.
- **Prompt B:** one independently copyable `text` block containing **exactly 100 space-separated words** in one paragraph about personality, acting, gestures, and speaking. Do not claim undocumented voice traits as fact.

In Stage 2.5, accept one final approved image per main speaker or an explicit `SKIP IMAGE` text-only fallback. Reuse a final image already supplied; never demand a duplicate upload. Inspect visible traits only, resolve differences from Prompt A with the student, then ask them to approve a short identity lock. Identify the image by **character name** in the student conversation, not its upload filename. Record every visible or approved recurring accessory (glasses, hat/headwear, jewelry, carried item) with its color, shape, and placement; distinguish fixed items from scene-specific props. Do not claim an image exists, is attached to Gemini/Flow, or has a confirmed asset handle unless that is actually established. Storyboard I begins only after the lock is approved.

### Copy-ready storyboard and video formats

Each stage's **storyboard image prompt** is one Markdown `text` fence. Its first line is exactly `Create a storyboard based on the panels below:`. Fill every panel from its approved global frame, with a title, `Dialogue:` and `Description:`. Descriptions cover one still moment, setting, composition, action, and reactions. Make the four panels a mini-arc: setup, response, escalation, and result. Each panel must show the effect of the preceding panel or the continuing goal, and Panel 4 must lead into the next group or complete the story. Before both fences, explain `Lead Character = [character name]` and tell the student to copy each fence separately. Inside each copyable fence, use `Lead Character` consistently in panel descriptions, speaker labels, the throughline, and the character lock. For history, refer to other real people by role and action; keep real people's names out of both copyable prompts, including titles and spoken text. Retain accurate names in the plan and historical notes outside them. Keep physical appearance and wardrobe in each closing character lock.

After Panel 4 and before the grid instructions, include `STORY THROUGHLINE:` with the **actual story-specific** goal and the links among these four panels, including the bridge from the previous group and to the next when applicable. Keep it in English and do not invent historical causation.

Inside every copy-ready **storyboard image** prompt, include this explicit output contract after the four panels:

```text
GRID LAYOUT INSTRUCTIONS:
- Generate exactly ONE 16:9 landscape storyboard IMAGE, not four separate images or a video.
- Divide the image into a 2×2 grid of four equal panels.
- Row 1: Panel 1 | Panel 2
- Row 2: Panel 3 | Panel 4
- Read left to right, then top to bottom; do not use a 1×4 strip.
- Separate adjacent panels with thin visible borders or dividers.
- Display each panel's number (1, 2, 3, 4) clearly in its upper-left corner.
- Keep each panel's scene and text inside its own border. Put character dialogue in a speech balloon and Narrator dialogue in a caption box; reproduce only the assigned Dialogue text. Silent panels have no dialogue text.
- Do not print panel titles, descriptions, story-throughline notes, layout instructions, or style notes in the image.
```

Close every storyboard image prompt with a self-contained `STYLE CONSISTENCY:` section containing:

- `VISUAL STYLE & IMAGE:` the approved style and one 16:9 landscape image containing the four 2×2 panels.
- `ENVIRONMENT LOCK:` detailed layout, landmarks, materials, props, light, era, weather, and time for every location used in that group. Repeat required details across prompts; never rely on “same as before.”
- `CHARACTER REFERENCE LOCK:` each relevant character's approved visual invariants under its image-prompt label, such as `Lead Character`. If an image was approved, call it **`Lead Character's approved character reference`** and use visible details plus agreed text details for anything hidden. If `SKIP IMAGE` was chosen, explicitly name Prompt A as the text-only reference. Repeat any fixed glasses, hat/headwear, jewelry, and other accessories with their approved color, shape, and placement in **every** group; do not invent absent items or turn scene props into permanent accessories. Do not redesign or swap identities.
- `IMAGE GENERATOR USAGE:` tell the student to attach the approved character image manually to the image generator when available; do not claim it is already attached.

The paired **video prompt** gets its own Markdown `text` fence. Begin with `Create one 16:9 animated video of four sequential scenes from this story. Play the scenes in order; use cuts between them, not a 2×2 grid.` Use the same four local `Panel 1`–`Panel 4` titles, speakers, spoken words, and outcomes as the storyboard image prompt. Give each panel a `Description:` of movement and camera action that remains historically supportable where relevant. Include `STORY THROUGHLINE:`, `VIDEO INSTRUCTIONS:` for one sequential video with Lead Character dialogue and off-screen Narrator voiceover, and a complete `STYLE CONSISTENCY:` with `VISUAL STYLE & VIDEO:`, `ENVIRONMENT LOCK:`, `CHARACTER REFERENCE LOCK:`, and `VIDEO GENERATOR USAGE:`. Repeat the approved clothing and fixed accessories, location geometry, period safeguards, and reference fallback in the video prompt itself. Do not add extra scenes, spoken words, or historical claims. State clearly that the student manually attaches an approved character image if available; never imply it is already attached.

**Never put an uploaded image filename, extension, path, generated image ID, or unconfirmed asset handle anywhere in either copy-ready prompt.** The image is supplied separately; each prompt refers to it by its stable label. Apply this rule to every panel and both `STYLE CONSISTENCY:` sections.

## Check the generated skill

Before finishing, confirm its frontmatter matches its folder; historical claims have sources or the original fictional world is explicitly declared fictional; the twelve beats form one connected story arc; every frame's consequence leads to the next; the image and video prompts carry that arc across group boundaries; the first student step asks for English or Bahasa Melayu dialogue; every line outside spoken `Dialogue:` remains English even after a Malay choice; the student workflow includes the image-or-skip decision and lock approval; Prompt B examples contain exactly 100 words; and all sample spoken lines have six or seven words in the chosen language. Check that each of the three stages delivers two separate, independently copyable prompts: one numbered 2×2 image with four equal panels and thin dividers, and one sequential four-scene video with matching titles and spoken words. Both must be text-only, self-contained, use a stable role label inside, repeat all fixed accessories in each `STYLE CONSISTENCY:` section, and avoid facts or names accidentally copied from another story.
