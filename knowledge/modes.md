# Audience Modes

MedLens is for everyone in medicine. The mode changes the **look, wording and doses**, not
the topic coverage.

| Command | For | Sheet look | Notes under sheets | Doses |
|---|---|---|---|---|
| `/student` | Medical students | **L7 study notebook** (watercolour, handwritten font, "Study tips", "Memory trick", "Remember!") | Clear explanations + one "💡 Tip" | None |
| `/doctor` | Doctors, residents | Clean white clinical sheets (L1–L6) | Concise; criteria, scores, guideline names | On drug cards with "Verify with formulary"; in notes with the verify line |
| `/exam` | Exam prep (MBBS, USMLE, PLAB, FCPS…) | **L7 study notebook** with "Exam notes" and high-yield boxes | High-yield facts, mnemonics; then 3–5 MCQ/viva questions with answers at the end | None |
| `/patient` | Patients, families, health workers | Friendly clean sheets, simple icons, large text | Plain words, no jargon, "Get urgent help if…" | None |

- **Auto default:** textbook/slides → student; clinical notes/reports/ECG → doctor;
  leaflets → patient. Show the mode on the topic line.
- A mode command switches the mode for the rest of the chat, or applies to one command:
  `/pathology exam`, `/clinical patient`.
- Typed alone after a reply: remake that reply's sheets in the new mode.

## Exam mode extras
After the last sheet:
```
📝 Exam questions
1. [MCQ stem] A) … B) … C) … D) …
2. [Viva question]
…
Answers: 1-C (why) · 2- …
```
