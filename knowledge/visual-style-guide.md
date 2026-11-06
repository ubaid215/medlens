# Visual Style Guide

Every image in a run must look like it belongs to the same textbook.

## Global style (append to every image prompt)

> Professional medical education illustration, high detail, clean composition, soft neutral
> background, consistent colour palette, sharp legible labels in a clean sans-serif font,
> no watermark, no patient identifiers, non-graphic. Small footer text: "MedLens · Educational use".

Aspect ratio: **landscape 3:2** by default; **portrait 2:3** for full-body maps and timelines.

## Image types

### 3D anatomical
- Photorealistic 3D render, soft studio lighting, subtle shadows.
- Cutaway, cross-section or exploded view to reveal internal structures.
- Realistic tissue colours: muscle red-brown, arteries red, veins blue, nerves yellow,
  bone ivory, fat pale yellow, lymph green.
- Neutral light-grey gradient background.

### Pathology split view
- Left: healthy. Right: diseased. Thin vertical divider. Headers "Normal" / "Disease".
- Optional circular magnified inset for microscopic view.

### Sequential panel (pathogenesis, procedure steps)
- 3–5 panels left→right, large numbers 1, 2, 3… in circles, one short caption each.

### Body map (clinical features, complications)
- Semi-transparent 3D human figure, relevant organs visible, callout lines to labels.

### Infographic / flowchart / timeline
- Flat clean vector style, white background, rounded boxes, arrows.
- Decision diamonds for yes/no points.

### Realistic clinical scene
- Photorealistic modern hospital setting (ward, ICU, OR, clinic, emergency bay).
- Professional staff in correct attire (scrubs, gloves, masks in OR), diverse people.
- Focus on the action being taught; non-graphic, no exposed wounds in detail, no blood pools.

### Patient counselling
- Warm, friendly semi-flat illustration, simple words, large icons.

## Colour coding (keep consistent across the whole run)

| Meaning | Colour |
|---|---|
| Normal / healthy | Green |
| Disease / abnormal | Red |
| Drug action / treatment | Blue |
| Warning / complication | Orange |
| Investigation / test | Purple |
| Urgent / red flag | Bold red banner |

## Labels

- 1–4 words each, **maximum ~8 labels per image**.
- Use standard terminology spelled exactly (write the label text in quotes in the prompt).
- Prefer abbreviations only when universal (ECG, MI, CT, ICU).
- No paragraphs, no doses, no small print inside images.
- Quiz mode: replace labels with numbers ①②③ only.
