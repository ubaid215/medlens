# Changelog

## 4.3.0 — 2026-11-14
- **`/medlens` explains the whole topic of the screenshot**: it lists every concept the
  source states and gives each its own sheet, showing the exact organs/structures, levels
  and numbers the source names. Nothing in the source is left out.
- **No fixed number of sheets** for `/medlens`, `/pathology`, `/tests`, `/clinical` (the
  3-per-reply cap from 4.2 is removed); each sheet must be a different part.
- Kept from 4.2: `/anatomy` and `/visualize` make exactly one image; each command stays in
  its own scope; no variations or automatic remakes; a screenshot with no command
  generates nothing.
- Welcome text is now "MedLens v4.3 ready".

## 4.2.0 — 2026-11-14
Fix from a real test: `/anatomy` made 1 atlas plate plus 6 near-identical "Cardiac Pain"
posters and used up the user's image quota.
- **Strict scope**: each command makes only its own content. `/anatomy` = exactly one atlas
  plate; `/visualize` = exactly one poster.
- **Usage limits**: other commands send at most 3 sheets per reply, then
  "Type continue for sheets N–M."
- **No automatic remakes or variations**: errors are named under the sheet; the user decides
  with `/redo N`.
- **Screenshot with no command generates nothing** (it used to run `/medlens`).
- Welcome text is now "MedLens v4.2 ready".

## 4.1.0 — 2026-11-14
- New **`/anatomy`**: one pure gross-anatomy atlas plate (white background, 3D cutaway,
  20–30 leader-line labels, heading "DETAILED ANATOMY OF THE HUMAN [ORGAN]"); no disease content.
- New **`/visualize`**: one comprehensive dark-navy overview poster — central 3D hero plus
  6–10 info cards chosen for the topic's category.
- Both take the topic from the uploaded screenshot (or typed after the command).
- New `examples/master-prompts.md` holds the two full prompts (user-written), with added
  exact label/card-text lists, read-back check, no doses/lab values, no logos.
- Welcome text is now "MedLens v4.1 ready". Other commands unchanged.

## 4.0.0 — 2026-11-13
Rebuilt the visual style from the user's reference infographics; fixed "no images generated".
- **Detailed infographic sheets** replace single-idea images: portrait 2:3 at the largest
  size, title band, hero visual, 4–8 sections, tip box. Model decides how many sheets.
- **7 layouts**: L1 atlas cross-section · L2 info rows · L3 step cards · L4 photo panel grid ·
  L5 drug cards · L6 proforma dashboard · L7 study notebook (student/exam look).
- **OPD drug cards** in `/clinical`: generic name · Use · How · **Why chosen** · Side effects ·
  Avoid in · Monitor; guideline named; doses only in `/doctor` with "Verify with formulary".
- **Images-first rule**: every command must generate sheets; never a text article; never
  web search, web images or links.
- **Text accuracy**: every word quoted in the prompt, readability limits, read-back after
  each sheet with remake on misspellings/wrong facts; no logos, handles or brands.
- Custom GPT setup: **Web Search off**. Quick install now pastes the instructions instead of
  a GitHub link.
- Claude mode builds sheets as HTML/SVG infographic sections; photo/3D heroes as prompts.
- New sample run (hypertension OPD drug cards); test updated.

## 3.0.0 — 2026-11-06
- **The model decides the number of images** per command from the topic; count shown on the
  topic line; `continue` resumes if the platform stops.
- `/medlens` now covers **anatomy, root cause and the exact starting point** of the disease,
  and ends with a **recommended next command** (OPD vs surgical vs emergency).
- `/pathology` = disease in depth (incl. histology, types/stages, prognosis).
- `/tests` = clinical examination (signs shown being performed) and diagnosis.
- `/clinical` replaces `/treatment`: **auto OPD** (which medicine, mechanism, why) or
  **Surgical** workflow (indications, pre-op, operative steps, post-op); force with
  `/clinical opd` / `/clinical surgical`.
- Audience modes back: `/student`, `/doctor`, `/exam` (adds MCQ/viva), `/patient`.
- `knowledge/image-sets.md` → `knowledge/command-coverage.md`; new `knowledge/modes.md`;
  5 new prompt templates (starting point, histology, exam sign, pre-op, post-op).
- Sample run now uses appendicitis (surgical pathway).

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
