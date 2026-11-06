# Tool — Claude Mode (no built-in image generator)

Claude cannot generate photographic or photorealistic images on its own, but it **can draw**
precise vector diagrams (SVG/HTML). Claude mode uses that strength:

- **Draw it** (SVG) — every image that is a diagram: flowcharts, timelines, ladders, body
  maps, mechanisms, comparison grids, labelled schematics, ECG strips, lab panels.
- **Prompt it** — only the images that need photorealism or 3D rendering: the user gets a
  ready-to-paste prompt, **plus** a labelled schematic drawn by Claude so they still learn
  from it immediately.

## 1. Detect the platform (silently, at the start of a run)

| Situation | Mode |
|---|---|
| A built-in image generation tool is available (ChatGPT) | **Image mode** — `tools/image-generation.md` |
| Claude with an image-generation tool/MCP connected | **Image mode** using that tool for photoreal images; still draw diagrams as SVG (more accurate labels) |
| Claude without any image tool | **Claude mode** — this file |

State the mode once on the Topic Card: `Renderer: Claude mode (diagrams drawn, prompts for 3D/photoreal)`.

## 2. Which renderer for each category

| # | Category | Claude mode renderer |
|---|---|---|
| 0 | Urgent Action | **Draw** — red banner card (`svg-templates.md` → Urgent card) |
| 1 | Normal anatomy | **Prompt** + **Draw** labelled schematic (simplified outline, leader lines) |
| 2 | Normal physiology | **Draw** — schematic with flow arrows |
| 3 | Causes & risk factors | **Draw** — hub-and-spoke |
| 4 | Pathogenesis | **Draw** — numbered sequential panels |
| 5 | Pathology | **Prompt** (3D split view) + **Draw** schematic normal vs disease |
| 6 | Clinical features | **Draw** — body map (`svg-templates.md` → Body map) |
| 7 | Investigations | **Draw** — ECG strip / lab panel with ↑↓ / imaging finding schematic |
| 8 | Diagnosis flow | **Draw** — flowchart |
| 9 | Non-drug management | **Draw** icon cards (+ **Prompt** for a realistic ward scene) |
| 10 | Pharmacology | **Draw** — target → drug → effect mechanism diagram |
| 10x | Treatment ladder | **Draw** — ladder |
| 11 | Procedure / surgery | **Prompt** (realistic scene) + **Draw** numbered step strip |
| 12 | Complications | **Draw** — body map with orange callouts |
| 13 | Follow-up & prevention | **Draw** — timeline |
| 14 | Patient counselling | **Draw** — 4 friendly icon cards |
| + | Differentials | **Draw** — comparison grid |
| + | User's own values | **Draw** — values against normal-range bars |

So in Claude mode roughly **75% of images are drawn directly**; only anatomy, pathology,
realistic scenes and procedures also get a prompt.

## 3. Output container

**Preferred — one HTML artifact called "MedLens — [condition]"** (works in Claude.ai and
the Claude apps):
- One `<section>` per plan image, in plan order, headed `[#]. [Title] · [Category]`.
- Inline `<svg>` diagram, then the caption block as HTML.
- For prompt images: the schematic SVG, then a box "🖼️ Realistic version — paste into any
  image generator" with the full prompt in a `<pre>` and a **Copy** button.
- Each batch (`/next`) **updates the same artifact**, appending the new sections, so the
  user ends with one complete visual study sheet. Keep earlier sections unchanged.
- Add a top bar: title, mode, `Images a–b of N`, and a small "Educational use only" note.
- Must work offline: inline CSS, no external images, system fonts.

**Fallback — no artifacts available** (e.g. API/terminal):
- Output each diagram as an ```` ```svg ```` code block followed by its caption, and each
  photoreal prompt as a ```` ```text ```` block. Tell the user once: "Save any SVG block as
  `.svg` to view it."

Chat text alongside the artifact stays short: Topic Card, Visual Plan, batch footer.
Captions live in the artifact (do not repeat them in chat).

## 4. Drawing rules (SVG)

- Use the shapes and colours in `examples/svg-templates.md`; keep `viewBox` fixed per type
  (landscape `0 0 900 600`, portrait `0 0 600 900`).
- Colour coding identical to `knowledge/visual-style-guide.md`:
  normal `#2E9E5B`, disease `#D64545`, treatment `#2F6FD6`, warning `#E8892B`,
  tests `#7B4FC9`, neutral text `#1F2933`, lines `#52606D`, panel fill `#F5F7FA`.
- Labels 1–4 words, max ~8, font-size ≥ 16 (viewBox units), never overlapping —
  place labels at the edges and use leader lines.
- Anatomical schematics: simplified but **topologically correct** (correct sides, order of
  structures, direction of flow). Prefer clear stylised outlines over failed realism.
  Do not attempt photorealistic drawing in SVG.
- Every diagram has a title (`<text>` at top) and the footer "MedLens · Educational use".
- Add `role="img"` and `<title>` / `<desc>` for accessibility.
- No doses in diagrams (same rule as images).
- Quiz mode: replace label text with ①②③; answers in a collapsed `<details>` at the end of
  the batch section.

## 5. Prompt images in Claude mode

Use the same templates as `examples/image-prompt-templates.md` (they are written for any
image generator). Present them as:

```
🖼️ Image [#] — realistic version
Paste into ChatGPT, Gemini, or any image generator:
[full prompt]
```

Never claim an image was generated when only a prompt was provided.

## 6. Quality check (silent, per diagram)
- [ ] Correct anatomy direction/side and order of structures
- [ ] Labels readable, not overlapping, spelled correctly
- [ ] Colour coding matches meaning
- [ ] Title + footer present
- [ ] Caption follows `examples/output-formats.md`
