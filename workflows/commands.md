# Commands — exact behaviour

Commands are case-insensitive. Accept them with or without `/` (`next` = `/next`).
Accept natural language equivalents ("make the next ones", "show only 3 and 7").

| Command | Needs | Behaviour |
|---|---|---|
| `/medlens` | Screenshot (new or the last one) | Full run (`workflows/full-run.md`). Replaces any previous plan. |
| *(screenshot only)* | Screenshot | Same as `/medlens`. |
| `/plan` | Screenshot | Steps 1–5 only. No images. User can then type `next` to start generating from image 1. |
| `/next` | Existing plan | Generate the next 4 images not yet generated. If all done → final summary. If no plan → ask for a screenshot. |
| `/next 6` | Existing plan | Next batch with 6 images instead of 4 (max 6). |
| `/only 3 7 10` | Existing plan | Generate exactly these numbers, in this order. Ranges allowed: `/only 3-6`. |
| `/redo 5` | Generated image 5 | Regenerate image 5 with the same plan line. |
| `/redo 5 <feedback>` | Generated image 5 | Regenerate applying the feedback (e.g. "show the valves larger", "more realistic", "fewer labels"). Keep everything else. |
| `/add <topic>` | Existing plan | Append new image(s) to the plan for that topic, show the new plan lines, then generate them. |
| `/student` | — | Switch mode. If a screenshot is attached → full run in this mode. |
| `/doctor` | — | Same, Doctor mode. |
| `/quiz` | Existing plan or screenshot | Quiz version of the plan (numbered blank labels, answers at end of batch). |
| `/patient` | Existing plan or screenshot | Patient plan (5–7 images, plain language). |
| `/summary` | Existing run | Show the final summary now, without generating remaining images. |
| `/help` | — | Show the command table from `SKILL.md`. |

## Edge cases
- **New screenshot mid-run**: ask "Start a new run for the new screenshot? (your current plan
  has X images left)". If the user just sends it with `/medlens`, start the new run.
- **Image generation fails / limit reached**: say which image failed, keep the plan, tell the
  user they can type `/only <n>` later to continue from there.
- **Image is wrong (anatomy/label error)**: apologise briefly, `/redo` automatically once with
  the correction; if still wrong, note the error in the caption.
- **User asks a question between batches**: answer it briefly, then remind:
  "Type **next** to continue with images X–Y."
