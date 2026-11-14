# Visual Style Guide — Medical Infographic Sheets

Every MedLens image is a **detailed, readable study sheet**: a portrait infographic that
fully clarifies one part of the topic. Think of a high-quality medical poster a student
would print and pin on the wall.

## 1. Sheet anatomy (every sheet)

```
┌──────────────────────────────┐
│  TITLE BAND (topic + part)   │  ← big bold title, short subtitle
├──────────────────────────────┤
│  HERO VISUAL                 │  ← 3D organ / cross-section / real clinical photo
│  + 4–8 SECTIONS              │  ← each: heading + icon/mini picture + 2–3 short lines
├──────────────────────────────┤
│  SUMMARY / TIP BOX           │  ← 💡 tip, quick summary or "Remember"
│  footer: MedLens · Educational use
└──────────────────────────────┘
```

- **Format:** portrait 2:3, the **largest size the image tool allows** (e.g. 1024×1536 or
  higher). Text must be readable on a phone without zooming.
- **One sheet = one part of the topic** (e.g. "Normal anatomy", "OPD drugs: first line",
  "Examination"). Several sheets per command when needed — the model decides.
- **No repeats across sheets:** each sheet covers a different part; the same hero visual is
  never used twice in a chat.

## 2. The 7 layouts

| Layout | Looks like | Use for |
|---|---|---|
| **L1 Atlas cross-section** | Hyper-detailed 3D cutaway in the centre, 15–30 colour-coded labels with thin leader lines around it, white background | Detailed anatomy (`/medlens`) |
| **L2 Info rows** | White sheet; left column of coloured rows (icon tile + bold term + small full name), middle column "what it means" + 1–2 lines, organ illustration on the right, summary box below | Causes, types, lab tests, complications |
| **L3 Step cards** | Numbered pastel cards stacked vertically (big number, heading, 1–2 lines, mini diagram); optional right column with normal vs abnormal examples | Mechanisms, interpretation methods (ECG, X-ray), diagnosis steps |
| **L4 Photo panel grid** | 4–6 panels in a grid; each has a heading, a real clinical photo of the technique, a ✓ checklist and a 💡 tip strip | Clinical examination techniques, special tests, procedures |
| **L5 Drug cards** | Pastel sections grouped by drug class/indication; each card: drug name, small icon, labelled lines (Use · How it works · Why · Side effects · Avoid in · Monitor) and a small mechanism picture | OPD medicines, emergency drugs |
| **L6 Proforma dashboard** | Dark navy background, glass-style panels around a central 3D organ; lettered sections A, B, C… | History-taking & examination format, case workup |
| **L7 Study notebook** | Spiral notebook page, watercolour drawings, handwritten-style font, boxes "Study tips", "Memory trick", "Exam notes", "Remember!" | `/student` and `/exam` versions of any sheet |

Default theme: **clean white medical** (L1–L5). L6 only for proforma/case-workup sheets.
L7 replaces the theme in `/student` and `/exam` modes.

## 3. Readability rules (critical — image text errors come from too much text)

- **Title:** ≤ 6 words. **Section heading:** ≤ 4 words, bold, coloured.
- **Section body:** ≤ 3 lines, ≤ 8 words per line. Short phrases, not sentences.
- **Total text per sheet:** about 120–180 words. More content → another sheet.
- **Sections per sheet:** 4–8. L1 atlas: up to 30 labels of 1–3 words.
- Large clear sans-serif font (L7: neat handwritten font), high contrast, no text over busy
  image areas.
- Write **every word of text inside quotes in the prompt**, spelled exactly; never let the
  image tool invent text.
- Medical terms spelled exactly as in the screenshot or standard textbooks.
- No paragraphs, no long tables, no tiny print, no watermarks.
- **No logos, social handles, websites or other brands.** Only the footer
  "MedLens · Educational use".

## 4. Colour system

| Meaning | Colour |
|---|---|
| Normal / healthy | Green |
| Disease / abnormal / injury | Red |
| Treatment / drug | Blue |
| Warning / complication / avoid | Orange |
| Test / investigation | Purple |
| Tip / summary | Yellow |
| Emergency | Bold red banner |

Section colours stay consistent within one reply. Anatomy uses realistic tissue colours
(arteries red, veins blue, nerves yellow, bone ivory, muscle red-brown, lymph green).

## 5. Hero visuals

- **Anatomy:** photorealistic 3D render, cutaway / cross-section, soft studio light.
- **Clinical photos (L4, surgical steps):** realistic, modern clinic or theatre, diverse
  people, correct attire, gloves, draping; **non-graphic** — no gore, no blood pools.
- **Organs in L2/L5:** clean semi-realistic illustration.
- **L7:** watercolour sketch style.

## 6. Accuracy read-back (after every sheet)

Read every word visible in the generated sheet and compare with the prompt text:
- any misspelling, invented word, wrong number, duplicated section, wrong level/side,
  impossible value (e.g. "45 °C") → **name the error under the sheet** and suggest `/redo N`.
- Never remake automatically: each image uses the user's daily quota.
