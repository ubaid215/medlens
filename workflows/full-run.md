# Workflow — any command

Same steps for `/medlens`, `/pathology`, `/tests` and `/clinical`.

## 1. Read (silent)
- Read the whole screenshot: text, values with units, diagrams, labels.
- Ignore names, IDs, dates of birth.
- Unreadable or unclear → ask **one** short question and stop.

## 2. Understand the topic (silent — do not show)
- Name the topic and the main disease behind it (for anatomy-only pages, the disease the
  concept explains).
- Copy levels, numbers and named structures exactly; keep separate statements separate.
- Mode: the user's last mode command, else auto (textbook/slides → student;
  clinical notes/reports → doctor; leaflets → patient).
- Emergency findings → first line "⚠️ Emergency — …".
- For `/clinical`: decide **OPD**, **Surgical** or **both** (see
  `knowledge/command-coverage.md`), unless the user forced one.
- Remember what was already drawn in this chat (no repeats).

## 3. Decide the images
- Go through the coverage list for the command in `knowledge/command-coverage.md`.
- Keep every point that matters for this topic; drop points that don't apply.
- One idea per image. Merge two tiny points into one image only if they share one picture;
  split a crowded point into two images.
- If a point's main picture was already drawn, choose a new angle, close-up or scene.
- The count is whatever this gives — no fixed number.

## 4. Make each image
1. Build the prompt: opening line + matching template (`examples/image-prompt-templates.md`)
   + style block. Labels in quotes, max 8.
2. Generate one image.
3. Check it: labels match the facts? one idea, not a poster? not a repeat? no doses?
   Wrong → remake once with a simpler prompt. Still wrong → say what is wrong in its note.
4. Write its note: "N. Title" + 2–4 bullets in the mode's wording.
5. If the platform stops, wait; on `continue`, carry on from the next image.

## 5. Finish the reply
- Exam mode: add "📝 Exam questions" (3–5 MCQ/viva) with answers at the end.
- `/medlens`: recommended next command with a few words why.
- Other commands: `👉 Next:` with the unused commands.
- `/clinical`: end with the safety line.
- Nothing else: no plans, tables, fact sheets or summaries.
