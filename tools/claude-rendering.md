# Tool — Claude Mode (no built-in image generator)

Claude cannot generate photorealistic images, but it **can build** rich HTML/SVG
infographic sheets with real, perfectly spelled text. Claude mode uses that: every sheet is
built as an HTML section in the same layout as the image version; only the photorealistic
hero visual (3D organ, clinical photo) becomes a ready-to-paste prompt.

## 1. When to use it

| Situation | Renderer |
|---|---|
| Built-in image generation available (ChatGPT) | Generate sheets — `tools/image-generation.md` |
| Claude with an image-generation tool connected | Build sheets in HTML; generate hero visuals with the tool |
| Claude without any image tool | **Claude mode** (this file) |

Say once, under the topic line: `Claude mode — sheets built as a page; prompts for 3D/photo visuals`.

## 2. Layouts in HTML/SVG

| Layout | Claude mode build |
|---|---|
| L1 Atlas cross-section | SVG outline sketch of the structure with numbered/coloured leader-line labels + **prompt** for the 3D render |
| L2 Info rows | HTML rows: coloured icon tile, bold term, meaning column, summary box; small SVG organ |
| L3 Step cards | Numbered pastel HTML cards with mini SVG diagrams (ECG strips, arrows) |
| L4 Photo panel grid | HTML grid of panels with checklists and tip strips; each photo slot = **prompt** |
| L5 Drug cards | Pastel HTML cards grouped by class: name, Use, How, Why, Side effects, Avoid in, Monitor (+ Dose in `/doctor` with "Verify with formulary"); tiny SVG mechanism icon |
| L6 Proforma dashboard | Dark navy HTML panels lettered A, B, C… around an SVG organ outline |
| L7 Study notebook | Paper-texture background, handwritten-style web-safe font, boxed "Study tips", "Memory trick", "Remember!" |

SVG building blocks: `examples/svg-templates.md`.

## 3. Output

**Preferred — one HTML artifact "MedLens — [topic]"**
- Portrait-proportioned sheets (max-width ~800px), one `<section>` per sheet, numbered,
  grouped under the command name; notes under each sheet.
- Hero prompt slots: a box "🖼️ Realistic visual — paste into any image generator" with the
  prompt in a `<pre>` and a **Copy** button.
- Each later command **updates the same artifact**, adding its sheets.
- Inline CSS, no external images, system fonts; footer "MedLens · Educational use".

**Fallback — no artifacts:** each sheet as an ```` ```html ```` or ```` ```svg ```` block;
prompts as ```` ```text ```` blocks. Tell the user once how to save and open them.

Chat text stays short: topic line and `👉 Next:` line.

## 4. Rules
- Same coverage, readability limits, colours and safety as the image version.
- Anatomy sketches simplified but correct (sides, order of structures, direction of flow).
- Never claim an image was generated when only a prompt was given.
