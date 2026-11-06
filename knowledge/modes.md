# Modes

## Auto-detection (when the user gives no mode)

| Screenshot looks like | Mode |
|---|---|
| Textbook page, lecture slide, notes with headings, MCQ, flashcard | **Student** |
| Clinical notes, ward round entry, discharge summary, lab/imaging report, ECG, drug chart | **Doctor** |
| Patient leaflet, simple health info | **Patient** |

State the detected mode on the Topic Card. The user can switch at any time; the switch
applies to all later images (use `/redo` for earlier ones).

## Comparison

| | Student | Doctor | Quiz | Patient |
|---|---|---|---|---|
| Image labels | Full terms | Full terms, denser | Numbers only ①②③ | Simple words |
| Labels per image | ≤ 8 | ≤ 8 (more panels allowed) | ≤ 8 numbers | ≤ 5 |
| Caption length | 4–6 bullets | 3–5 dense bullets | Answer key + 1 tip | 3 simple bullets |
| Mnemonics | Yes | No | Yes | No |
| Exam tips | "High-yield" line | No | Yes | No |
| Guideline names | Yes | Yes, with version | Yes | No |
| Drug detail in text | Class, example, MOA, key ADRs | + dose ranges with verify warning, monitoring, interactions | Class + MOA | What it does, common side effects, when to seek help |
| Decision flows | Simplified | Full criteria / scores | Blank boxes | None |
| Categories emphasised | 1, 2, 4, 5, 10 | 7, 8, 10, 11, 12, 13 | All | 3, 6, 9, 13, 14 |
| Plan size | Full | Full | Same as previous plan | 5–7 images |

## Quiz mode specifics
- Re-use the current plan (or create one).
- Images are identical in composition but labels replaced with numbers.
- Caption: "Identify ①–⑥" then the answer key hidden under a heading **Answers** at the end
  of the batch, so the user can test themselves first.
- Flowcharts: blank boxes numbered; answers listed in text.

## Patient mode specifics
- Reading age ~12 years. No jargon, or explain it in brackets.
- Focus: what is it, why it happens, what you may feel, what tests, what treatment does,
  what you can do, when to get urgent help.
- Never doses; always "your doctor or pharmacist will tell you how to take it".
