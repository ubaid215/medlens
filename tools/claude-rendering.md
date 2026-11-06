# Tool — Claude Mode (no built-in image generator)

Claude cannot generate photorealistic images, but it **can draw** precise diagrams (SVG).
Claude mode uses that: diagrams are drawn directly; 3D anatomy and realistic hospital scenes
get a labelled sketch **plus** a ready-to-paste prompt for any image generator.

## 1. When to use it

| Situation | Renderer |
|---|---|
| Built-in image generation available (ChatGPT) | Generate images — `tools/image-generation.md` |
| Claude with an image-generation tool connected | Draw diagrams as SVG; use the tool for 3D/realistic slots |
| Claude without any image tool | **Claude mode** (this file) |

Say once, under the topic line: `Claude mode — diagrams drawn, prompts for 3D/realistic images`.

## 2. How each slot is rendered

| Command | Slot | Claude mode |
|---|---|---|
| `/medlens` | 1 Structure | Sketch + **prompt** (3D) |
| | 2 How it works | **Draw** — flow arrows or numbered panels |
| | 3 What the patient feels | **Draw** — body map |
| | 4 Key point | **Draw** — body map, comparison or focused schematic |
| `/pathology` | 1 Causes | **Draw** — hub-and-spoke |
| | 2 Disease process | **Draw** — numbered panels |
| | 3 Healthy vs diseased | Sketch + **prompt** (3D split view) |
| | 4 Complications | **Draw** — body map with orange callouts |
| `/tests` | 1 Bedside signs | **Draw** — body map |
| | 2–3 Key tests | **Draw** — ECG strip / lab bars / imaging schematic |
| | 4 Diagnosis path | **Draw** — flowchart |
| `/treatment` | 1 Treatment plan | **Draw** — ladder or flow |
| | 2 Main medicine | **Draw** — mechanism diagram |
| | 3 Procedure / surgery | Sketch + **prompt** (realistic scene) |
| | 4 Recovery & prevention | **Draw** — icon cards / timeline |

Templates: `examples/svg-templates.md`.

## 3. Output

**Preferred — one HTML artifact "MedLens — [topic]"**
- A heading per command (Explain, Pathology, Tests, Treatment), then 4 sections `1.`–`4.`
  each with the SVG and its notes.
- Prompt slots add a box "🖼️ Realistic version — paste into any image generator" with the
  prompt in a `<pre>` and a **Copy** button.
- Each later command (`/pathology`, `/tests`, `/treatment`) **updates the same artifact**,
  adding its 4 sections, so the user ends with one study sheet.
- Inline CSS, no external images, system fonts.

**Fallback — no artifacts:** each diagram as an ```` ```svg ```` block with its notes; each
prompt as a ```` ```text ```` block. Tell the user once to save SVG blocks as `.svg` files.

Chat text stays short: the topic line and the `Next:` line. Notes live in the artifact.

## 4. Drawing rules
- Use the shapes and palette in `examples/svg-templates.md`
  (normal `#2E9E5B`, disease `#D64545`, treatment `#2F6FD6`, warning `#E8892B`,
  tests `#7B4FC9`, text `#1F2933`, lines `#52606D`, panel `#F5F7FA`).
- Labels 1–4 words, max 8, font-size ≥ 16, never overlapping — labels at the edges with
  leader lines.
- Anatomy sketches: simplified but correct (sides, order of structures, direction of flow).
- Title + footer "MedLens · Educational use"; `role="img"` and `<title>`.
- No doses in diagrams.

## 5. Prompt slots
Use `examples/image-prompt-templates.md`. Present as:
```
🖼️ Image [#] — realistic version
Paste into ChatGPT, Gemini, or any image generator:
[full prompt]
```
Never claim an image was generated when only a prompt was given.
