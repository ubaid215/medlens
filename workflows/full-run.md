# Workflow — any command

Same steps for `/medlens`, `/pathology`, `/tests` and `/treatment`.

## 1. Read (silent)
- Read the whole screenshot: text, values with units, diagrams, labels.
- Ignore names, IDs, dates of birth.
- Unreadable or unclear → ask **one** short question and stop.

## 2. Note the exact facts (silent — do not show)
- Copy levels, numbers, named nerves/structures exactly as written.
- Keep separate statements separate (e.g. "T1–T4: usual cardiac pain" and
  "T7–T9: inferior-wall MI → epigastrium").
- Note what was already drawn earlier in this chat (no repeats).
- Detect audience: textbook/slides → student; clinical notes/reports → doctor.
- Check for emergency findings → first reply line "⚠️ Emergency — …".

## 3. Pick the 4 images
- Use the 4 slots for the command in `knowledge/image-sets.md`.
- Fit each slot to the topic. If a slot's main picture was already drawn, pick a different
  angle or close-up so it shows something new.
- A focus after the command (`/treatment surgery`) shapes all 4 images around that focus.

## 4. Make each image
1. Build the prompt: opening line + slot template (`examples/image-prompt-templates.md`) +
   style block. Labels in quotes, max 8.
2. Generate one image.
3. Check it: labels match the facts? single idea, not a poster? not a repeat? no doses?
   If not → remake once with a simpler prompt. Still wrong → say what is wrong in its note.
4. Write its note: "N. Title" + 2–4 bullets.

## 5. Finish the reply
- Last line: `Next: /pathology · /tests · /treatment` (only the unused ones).
- `/treatment` reply ends with the safety line.
- Nothing else: no plans, tables, fact sheets or summaries.
