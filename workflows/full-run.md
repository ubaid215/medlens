# Workflow — Full Run (`/medlens`)

Follow these steps in order. Do not skip steps 1–4 even for short screenshots.

## Step 1 — Read the screenshot
- Read everything: headings, body text, tables, values with units, diagrams, arrows,
  image labels, handwriting where legible.
- Note the screenshot **type** (textbook, slide, clinical notes, lab report, imaging report,
  ECG, drug chart, MCQ).
- Ignore and never repeat patient identifiers.
- If unreadable/ambiguous → ask **one** clarifying question and stop.

## Step 2 — Extract topics
Build an internal list:
- **Conditions** (primary + secondary/differentials mentioned)
- **Organ systems / structures**
- **Key findings** (symptoms, signs, values, imaging findings) — only what is shown
- **Treatments / drugs / procedures** mentioned
- **Gaps**: standard topics the screenshot does not mention but are needed to understand it

## Step 2b — Fact Sheet (show to user)
Copy every exact fact from the screenshot **verbatim**: spinal levels, numbers, values with
units, named nerves/vessels/structures, criteria, drug names. One fact per line.
- Keep separate statements separate. Example from a cardiac-pain page:
  "Afferents enter via posterior roots of the upper four thoracic nerves (T1–T4)" and
  "Inferior-wall/diaphragmatic MI: afferents enter T7–T9 → epigastric pain" are two facts.
- If the source conflicts with standard teaching, keep the source fact and add
  "⚠️ note: [standard teaching]".
- Every image label later must match this sheet or well-established knowledge.

## Step 3 — Topic Card (show to user)
Use the format in `examples/output-formats.md`. Include detected mode and red flags.

## Step 4 — Red-flag check
Check against `knowledge/safety-rules.md` §3. If any red flag: add **Urgent Action** as
image #1 and mention it on the Topic Card.

## Step 5 — Visual Plan (show to user)
- For each condition, go through all 14 categories in `knowledge/coverage-checklist.md`
  plus the extras **and the Clinical Block** (investigations, diagnosis flow, pharmacology,
  management — "➕ beyond source" if not in the screenshot). Minimum 8 images per condition.
- Each plan line names ONE concept and the NEW element it shows. Check the plan against the
  No-Repeat rule before showing it: no two images may share the same main subject.
- Number images continuously (1…N). Group by condition, then by category.
- Each line: number · category · title · one-line description · style.
- State total N and number of batches (N ÷ 4, rounded up).
- For `/plan`, stop here.

## Step 6 — Generate batch
For each image in the batch (default 4):
1. Build the prompt from `examples/image-prompt-templates.md` + global style from
   `knowledge/visual-style-guide.md` + mode rules from `knowledge/modes.md`.
2. Put exact label text in quotes in the prompt. Max ~8 labels.
3. Generate **one** image with the built-in image tool (see `tools/image-generation.md`).
   **Claude mode** (no image tool): draw the diagram as SVG using `examples/svg-templates.md`
   and add it as a section of the run's HTML artifact; for 3D/photoreal categories draw a
   labelled schematic and add the paste-ready prompt (see `tools/claude-rendering.md`).
   Each `/next` updates the same artifact.
4. **Self-check** the generated image: read every visible label and compare with the Fact
   Sheet; check it is a single concept (not a poster) and that its main subject is not
   already in the No-Repeat Ledger. If anything fails → regenerate once automatically with a
   corrected, simpler prompt. If it still fails, state the exact error in the caption
   ("⚠️ Image shows 'T1–T5'; correct is T1–T4").
5. Add the image's elements to the No-Repeat Ledger.
6. Immediately after the image, write the caption block (format in
   `examples/output-formats.md`).

After the batch:
> ✅ Images 1–4 of N done. Type **next** for 5–8 · `/redo <n>` to fix one · `/only <n…>` to jump.

Stop and wait for the user.

## Step 7 — Continue
On `next` / `/next`: generate the next 4 from the plan. Keep the same style and colours.

## Step 8 — Final summary (after the last image)
- 5–8 bullet key points (high-yield in Student mode).
- Treatment summary in one line per line of therapy.
- **Sources**: guidelines named during the run.
- Safety footer from `knowledge/safety-rules.md` §7.
- Offer: `/quiz` to test yourself · `/patient` for a patient version · `/redo <n>`.

## Quality check before each image (silent)
- [ ] One clear teaching purpose — not a poster, no text boxes or paragraphs
- [ ] Main subject not already drawn (No-Repeat Ledger)
- [ ] Every level/number/structure matches the Fact Sheet exactly
- [ ] Labels ≤ 8, spelled correctly, in quotes
- [ ] No doses in the image
- [ ] Colour coding consistent with earlier images
- [ ] Nothing invented beyond the screenshot + standard knowledge
- [ ] Non-graphic, no identifiers
- [ ] Footer "MedLens · Educational use"
