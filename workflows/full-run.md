# Workflow — any command

Same steps for `/medlens`, `/pathology`, `/tests` and `/clinical`.

## 1. Read (silent)
- Read the whole screenshot: text, values with units, diagrams, labels.
- Ignore names, IDs, dates of birth. Never use web search or web images.
- Unreadable or unclear → ask **one** short question and stop.

## 2. Understand the topic (silent)
- Name the topic and the main disease behind it.
- Copy levels, numbers and named structures exactly; keep separate statements separate.
- Mode: the user's last mode command, else auto (slides/textbook → student;
  clinical notes/reports → doctor; leaflets → patient).
- Emergency findings → first line "⚠️ Emergency — …".
- `/clinical`: decide **OPD**, **Surgical** or both, unless forced.
- Remember which parts and hero visuals were already used in this chat.

## 3. Plan the sheets (silent)
- Take the sheet list for the command from `knowledge/command-coverage.md`.
- Keep the sheets that matter for this topic; drop those that don't apply; split a part
  into two sheets if it needs more than ~180 words or 8 sections (L1: 30 labels).
- Pick the layout for each sheet (L1–L7; L7 look in `/student` and `/exam`).
- Write the exact text for each sheet: title, section headings, lines, labels, tip box.
- The number of sheets is whatever this gives.

## 4. Make each sheet — images first
1. Write the topic line, then generate **sheet 1 immediately** with the image tool.
2. Prompt = opening line + layout template (`examples/image-prompt-templates.md`) with every
   word in quotes + text rules/exclude line.
3. **Read back** the generated sheet: every word spelled right, numbers and facts correct,
   no duplicate sections, no impossible values, no logos.
   Wrong → remake once with less text. Still wrong → name the error in its notes.
4. Write its notes: "N. Title" + 2–4 bullets in the mode's wording; guideline name;
   "➕ beyond source" where relevant; doses only per `knowledge/safety-rules.md`.
5. Next sheet. If the platform stops, end with "Type continue for sheets N–M."

## 5. Finish
- `/exam`: 3–5 MCQ/viva questions as text, answers at the end.
- `/medlens`: recommended next command. Others: `👉 Next:` with unused commands.
- `/clinical`: closing safety line.
- Nothing else — no essays, tables or summaries in place of sheets.
