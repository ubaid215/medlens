# Changelog

## 2.0.0 — 2026-11-06
Simplified after user testing: too many images, complicated commands, dense poster images.
- **4 images per command**, one idea each, short notes. No plans, fact sheets or tables in replies.
- New simple commands: `/medlens` (explain) · `/pathology` (what goes wrong) · `/tests`
  (diagnosis) · `/treatment` (which medicine or surgery, and why) · `/redo N` · `/help`.
- Removed: `/plan`, `/next`, `/only`, `/add`, `/summary`, `/student`, `/doctor`, `/quiz`,
  `/patient` (audience is now detected automatically).
- New `knowledge/image-sets.md` (the 4 slots per command); removed `coverage-checklist.md`
  and `modes.md`.
- Kept from 1.2: no posters, no repeats, exact facts, no doses inside images.
- Emergency findings now give a warning line instead of an extra image.

## 1.2.0 — 2026-11-06
Fixes from the first real ChatGPT test (cardiac pain page): only 4 images, poster-style
images repeating the same heart/spine/patient, wrong spinal levels (T2–T9, T1–T5), no treatment.
- **Single-concept images, no posters**: every prompt starts with a "NOT an infographic
  poster" line; no text boxes, paragraphs or brand titles inside images.
- **No-Repeat Ledger**: each image must show a new element; hero elements used once.
- **Fact Sheet**: exact facts copied from the source; labels must match; separate ranges never merged.
- **Self-check + auto-redo** of each image against the Fact Sheet.
- **Clinical Block always included** (investigations, diagnosis, drugs, management) marked
  "➕ beyond source"; minimum 8 images per condition.
- **Fixed welcome text** to confirm the GPT is really running MedLens.
- Setup guide: use the Configure tab only, never the Create chat.
- New regression test: `examples/test-cardiac-pain.md`.

## 1.1.0 — 2026-11-06
- **Claude mode**: when no image generator exists, MedLens draws diagrams itself as SVG
  (flowcharts, timelines, ladders, body maps, mechanisms, ECG strips, lab charts, risk
  factors, differentials, urgent cards, patient cards) in one HTML artifact that grows with
  each `/next`. 3D anatomy, pathology and realistic scenes get a labelled schematic plus a
  ready-to-paste prompt.
- New files: `tools/claude-rendering.md`, `examples/svg-templates.md`.
- Topic Card now shows the renderer. README explains Claude install and what each platform gives.

## 1.0.0 — 2026-11-06
- First release for ChatGPT (Custom GPT + install-by-link).
- Full-coverage image planning: 14 categories + extras (urgent, differentials, staging,
  treatment ladder, user's own values).
- Commands: /medlens, /plan, /next, /only, /redo, /add, /student, /doctor, /quiz, /patient,
  /summary, /help.
- Batching (4 per reply), consistent visual style and colour coding.
- Safety rules: no doses in images, guideline naming, red-flag urgent image, privacy.
