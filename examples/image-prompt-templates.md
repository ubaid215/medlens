# Prompt Templates — Infographic Sheets

Fill every `[bracket]` with **exact text** (in quotes). Never let the image tool invent
words. Keep within the readability rules in `knowledge/visual-style-guide.md`.

**Start every prompt with:**
> High-resolution portrait medical education infographic, 2:3, largest available size,
> crisp readable text, clean professional layout.

**End every prompt with:**
> TEXT RULES: use ONLY the quoted text, spelled exactly; no other words; large clear
> sans-serif font; high contrast. EXCLUDE: logos, watermarks, social handles, websites,
> brand names, paragraphs, tiny print, gore. Footer small text: "MedLens · Educational use".

---

## L1 — Atlas cross-section (detailed anatomy)
```
Detailed photorealistic 3D anatomical cross-section of the [ORGAN/REGION], [view: e.g.
coronal cutaway of the right ear], centred on a white background, soft studio lighting,
realistic tissue colours. Title at top: "[Title]". Around it, [N ≤ 30] labels with thin
leader lines pointing exactly to each structure, colour-coded by part
([part A] = [colour], [part B] = [colour]):
"[label 1]", "[label 2]", … (each 1–3 words).
Optional small subtitle: "[subtitle]".
```

## L2 — Info rows (causes, types, labs, complications)
```
Clean white medical infographic. Title band: "[Title]" with subtitle "[subtitle]".
Left side: [4–8] stacked rows, each with a coloured square icon tile ([icon idea]) and:
Row 1: bold term "[term]", small text "[full name]", right column heading "[meaning]"
and line "[≤ 8 words]".
Row 2: …
Right side: semi-realistic illustration of [ORGAN/BODY] with [highlight].
Bottom box "Quick summary": "[point 1]" · "[point 2]".
```

## L3 — Step cards (mechanism, interpretation, diagnosis steps)
```
Medical infographic with [4–7] numbered pastel cards stacked vertically
(each a different soft colour). Title: "[Title]", subtitle "[subtitle]".
Card 1: big number "1", heading "[heading]", line "[≤ 8 words]", small diagram of [x].
Card 2: …
[Optional right column: [2–3] example boxes, each with heading "[normal/abnormal name]",
a small diagram of [finding], and bullets "[…]", "[…]".]
Bottom tip strip with lightbulb: "[tip]".
```

## L4 — Photo panel grid (examination, special tests, procedures)
```
Clean light-blue and white medical infographic, grid of [4–6] panels.
Title: "[Title]", subtitle "[subtitle]".
Panel 1: number "1", heading "[technique]", small line "[what it checks]", realistic
clinical photo of a clinician performing [technique] on a draped adult patient
([position]), checklist: "✓ [point]", "✓ [point]", "✓ [point]", tip strip "Tip: [tip]".
Panel 2: …
Bottom row "Quick reminders": icons with "[word]" + "[short line]" ×[3–5].
Non-graphic, professional, diverse people.
```

## L5 — Drug cards (OPD medicines)
```
Clean pastel medical drug-reference infographic. Title: "[Condition]: [first-line /
add-on] medicines". Sections grouped by [drug class or indication], each with a coloured
header "[class]". Each drug card:
drug name "[generic name]" in bold, small icon ([tablet/inhaler/injection]),
lines labelled: "Use: [≤ 6 words]", "How: [mechanism ≤ 8 words]",
"Why: [reason chosen ≤ 8 words]", "Side effects: [≤ 6 words]",
"Avoid in: [≤ 6 words]", "Monitor: [≤ 5 words]",
[Doctor mode only: "Dose: [exact text]" and small red text "Verify with formulary"]
and a tiny mechanism picture of [target organ/receptor].
[2–6] cards total. Bottom box "Remember": "[point]".
```

## L6 — Proforma dashboard (history & examination format, case workup)
```
Dark navy medical dashboard infographic with glowing glass-style panels around a central
photorealistic 3D [ORGAN]. Title: "[Specialty/Topic] Case Proforma", subtitle
"[subtitle]". Lettered panels:
"A. [section]": "[item]", "[item]", "[item]"
"B. [section]": …
(up to 10 panels, each ≤ 4 short items, small icons).
Bottom row: "[Investigations]", "[Diagnosis]", "[Plan]" panels.
No sample patient data, no numbers in vital signs.
```

## L7 — Study notebook (student / exam mode)
```
Spiral-bound notebook page on textured paper, soft watercolour illustrations, neat
handwritten-style font, red and blue ink accents, small hearts and doodles.
Title: "[Title]". Central watercolour drawing of [STRUCTURE] with labels
"[label]", "[label]", … (≤ 10) and hand-drawn arrows.
Boxes: "Study Tips" — "[mnemonic]"; "Quick Facts!" — "[fact]";
"Exam Notes" — "[fact]"; "Memory Trick!" — "[trick]"; "Remember!" — "[point]".
```

## Surgical steps (variant of L4)
```
Clean white surgical workflow infographic, [4–6] numbered panels in order.
Title: "[Operation]: step by step".
Panel 1: heading "[step]", realistic photo-style image of [action] in a modern operating
theatre, sterile drapes, gowned and gloved team, line "[why this step ≤ 8 words]".
…
Side strip "Before surgery": "[item]", "[item]", "[item]".
Bottom strip "After surgery": "[item]", "[item]", "[item]".
Non-graphic, clean surgical field.
```

## Redo
`/redo N [fix]`: "Revise the previous infographic: [fix]." then repeat the full prompt with
the fix applied (usually less text or corrected words).
