---
name: story-skills
description: Create or update a self-contained, topic-locked classroom skill that guides students from a researched 12-scene history plan to character prompts and three text-only Google Flow or Gemini storyboards. Use when building a specialized storyboard skill, not when running one with students.
---

# Classroom Storyboard Skill Builder

This is the **authoring template**, not a student-facing Merdeka lesson. Create or update a specialized `<topic>-storyboard-classroom/SKILL.md` for the requested story. The existing [Merdeka](merdeka-storyboard-classroom/SKILL.md), [Parameswara](parameswara-storyboard-classroom/SKILL.md), and [Fall of Melaka](fall-of-melaka-storyboard-classroom/SKILL.md) skills show the intended student experience. Use them as examples; do not copy their facts, character designs, or source claims into another topic.

The generated `SKILL.md` must work on its own. Include its complete topic, twelve locked beats, factual sources, character design, student commands, prompt formats, and checks. Do not make it depend on this template or another skill file at runtime. Preserve an existing specialized skill's approved topic and distinctive facts when editing it.

## Build the topic-specific skill

1. Use the teacher's story, audience, style, and cast when provided. Default to Malaysian primary and lower-secondary students, English for all non-dialogue text, and cinematic 3D family animation. At the first student step, ask whether **Dialogue** should be in English or Bahasa Melayu; do not choose for the student.
2. Research historical claims with authoritative sources. Put direct source links and the facts they support **inside the generated skill**. Choose exactly twelve chronological, filmable beats. Keep legends, disputed details, and artistic reconstructions distinct from documented history. Include topic-specific visual safeguards such as period flags, buildings, clothing, and chronology. Do not invent precise dialogue, appearance, interiors, dates, or source-backed claims.
3. Choose only the named main speaking characters the story needs; one historical lead plus an off-screen Narrator is the default in this repository. Every designed main character must speak in the plan. The Narrator needs no character image prompt; silent participants and crowds need no profile. Give each main speaker a fixed written design, while marking unsupported traits as reconstruction.
4. Write a unique lowercase hyphenated frontmatter `name` matching the skill folder and a description that names the fixed story and output. Make the lesson topic-locked: students may revise pacing, framing, or tone, but cannot switch its event or silently replace its twelve beats.
5. Write the student workflow and copy-ready prompt architecture below into the generated skill, replacing generic labels with actual character names, historical beats, and safeguards. Keep the generated file focused; add extra files only when the topic needs them.

## Rules every generated classroom skill must carry

### Text-only production contract

- The assistant writes prompts and may inspect user-uploaded images read-only. It never generates, edits, renders, previews, uploads, delegates, or sends image, audio, animation, or video media. `Create a storyboard based on the panels below:` is text for the student to copy, not an instruction for the assistant to execute.
- Plan **twelve** chronological frames, grouped 1–4, 5–8, and 9–12. Each frame is an **individual 16:9 landscape video** scene; a four-panel prompt does not request a combined grid, still image, or vertical video.
- Deliver **three standalone four-panel prompts**, one per assistant reply. Use local `Panel 1`–`Panel 4` labels in every prompt and keep each prompt usable without the preceding ones.
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
| 3. Storyboard I | Approve reference lock | One prompt for global Frames 1–4 |
| 4. Storyboard II | `NEXT` | One prompt for global Frames 5–8 |
| 5. Storyboard III | `NEXT` | One prompt for global Frames 9–12; finish |

Recognize `START`, `NEXT`, `RETRY`, `HELP`, `SKIP IMAGE`, and the English/Malay language choice case-insensitively. Do not create the plan until the student chooses a dialogue language; if they type `START` or `NEXT` first, ask the language question and wait. Once chosen, proceed to Stage 1 without another command and remember the choice for every later `Dialogue:` field. `NEXT` otherwise advances only one stage and cannot skip the reference decision or approval gate. `RETRY` revises the current stage without changing the fixed topic. `HELP` briefly gives the current stage and one next action. Ask before restarting work already in progress. After the third storyboard, `NEXT` says the project is complete.

After a Bahasa Melayu choice, the Stage 1 reply must still begin in English, for example: `Dialogue language: Bahasa Melayu. Here is the 12-scene plan.` Continue with English prose and the exact English headings `Frames 1–4`, `Frame 1 —`, and `Historical fact:`; never translate them to `Kumpulan`, `Bingkai`, or `Fakta Sejarah`. Only the spoken text in `Dialogue:` may be Malay. Do not repeat or translate the welcome message.

In Stage 1, show each frame's factual anchor, filmable action, shot, speaker or cast, dialogue or silence, period environment, and continuity. Keep a consistent internal world description for repeated locations: layout, fixed landmarks and props, light, weather, era, and camera geography. The twelve approved beats remain in order throughout the three prompts.

In Stage 2, give each main speaker:

- **Character information:** role, dialogue frames, approved or reconstructed appearance, clothing, personality, and speaking style.
- **Prompt A:** one independently copyable `text` block for a single full-body character reference image on a clean studio background, with face, hair, build, clothing, colors, and accessories; no setting, other people, text, or watermark. This is a written prompt only.
- **Prompt B:** one independently copyable `text` block containing **exactly 100 space-separated words** in one paragraph about personality, acting, gestures, and speaking. Do not claim undocumented voice traits as fact.

In Stage 2.5, accept one final approved image per main speaker or an explicit `SKIP IMAGE` text-only fallback. Reuse a final image already supplied; never demand a duplicate upload. Inspect visible traits only, resolve differences from Prompt A with the student, then ask them to approve a short identity lock. Identify the image by **character name**, not its upload filename. Do not claim an image exists, is attached to Gemini/Flow, or has a confirmed asset handle unless that is actually established. Storyboard I begins only after the lock is approved.

### Copy-ready storyboard format

Each final prompt is one Markdown `text` fence. Its first line is exactly `Create a storyboard based on the panels below:`. Fill every panel from its approved global frame, with a title, `Dialogue:` and `Description:`. Descriptions cover the individual video scene, period setting, camera, action, and reactions. Refer to people by **name and action**; keep their physical appearance and wardrobe in the closing character lock.

Close every prompt with a self-contained `STYLE CONSISTENCY:` section containing:

- `VISUAL STYLE & VIDEO:` the approved style and four separate 16:9 landscape video scenes.
- `ENVIRONMENT LOCK:` detailed layout, landmarks, materials, props, light, era, weather, and time for every location used in that group. Repeat required details across prompts; never rely on “same as before.”
- `CHARACTER REFERENCE LOCK:` each relevant named character's approved visual invariants. If an image was approved, call it only **`[Character name]'s approved character reference`** and use visible details plus agreed text details for anything hidden. If `SKIP IMAGE` was chosen, explicitly name Prompt A as the text-only reference. Do not redesign or swap identities.
- `GOOGLE FLOW USAGE:` tell the student to attach the approved image manually to Gemini/Flow when available; do not claim it is already attached.

**Never put an uploaded image filename, extension, path, generated image ID, or unconfirmed asset handle anywhere in the copy-ready storyboard prompt.** The image is supplied separately; the prompt refers to it by character name. Apply this rule to every panel and the entire `STYLE CONSISTENCY:` section.

## Check the generated skill

Before finishing, confirm its frontmatter matches its folder; the fixed topic and twelve beats have suitable sources; the first student step asks for English or Bahasa Melayu dialogue; every line outside spoken `Dialogue:` remains English even after a Malay choice; the student workflow includes the image-or-skip decision and lock approval; Prompt B examples contain exactly 100 words; all sample spoken lines have six or seven words in the chosen language; and the three storyboard groups have four local panels each. Check that the generated skill is text-only, self-contained, uses character names rather than image filenames, and does not contain facts or names accidentally copied from another story.
