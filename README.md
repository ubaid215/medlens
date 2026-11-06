# MedLens 🩺

**Medical screenshot → 4 clear images per command.**

Send a screenshot of a textbook page, lecture slide, clinical notes or a report. Type a
command and MedLens makes **4 simple images**, one idea each, with short notes.

Built for **medical students** and **doctors**. Runs inside ChatGPT with its built-in image
generation — **no API key needed**.

> ⚠️ Educational use only. Not a diagnostic tool and not a substitute for clinical judgement,
> local guidelines or a prescriber.

---

## Use

| Command | 4 images about |
|---|---|
| `/medlens` | **Explain** — structure · how it works · what the patient feels · key point |
| `/pathology` | **What goes wrong** — causes · disease process · healthy vs diseased · complications |
| `/tests` | **Diagnosis** — bedside signs · key test · second test · diagnosis path |
| `/treatment` | **What we do and why** — treatment plan · main medicine · procedure/surgery · recovery |
| `/redo 2` | Remake image 2 (add what to fix: `/redo 2 bigger labels`) |
| `/help` | Command list |

Start with `/medlens`, then use the others in any order. Add a focus if you like:
`/treatment surgery`.

---

## Install

### Option A — Custom GPT (recommended)
Follow [`setup/custom-gpt-setup.md`](setup/custom-gpt-setup.md): paste
`instructions/gpt-instructions.md` into **Configure → Instructions**, upload the knowledge
files, turn on **Image Generation**.

### Option B — Paste the GitHub link into a ChatGPT chat
Use the prompt in [`setup/install-by-link.md`](setup/install-by-link.md). Works for that chat
only and needs web access.

### Option C — Claude
Zip the repository (`SKILL.md` inside the top folder) and upload it in
**Settings → Capabilities → Skills**. Claude has no image generator, so it runs in
**Claude mode**: diagrams (flows, body maps, mechanisms, ECGs, treatment plans) are drawn
directly; 3D anatomy and realistic hospital scenes come as a labelled sketch plus a prompt
to paste into any image generator.

---

## Folder structure

```
medlens/
├── SKILL.md                         Instructions (entry point)
├── instructions/gpt-instructions.md Instructions for the Custom GPT (< 8000 chars)
├── knowledge/
│   ├── image-sets.md                  the 4 images for each command
│   ├── visual-style-guide.md          how images look
│   └── safety-rules.md                medical guardrails
├── workflows/
│   ├── full-run.md                    steps for any command
│   └── commands.md                    command details
├── tools/
│   ├── image-generation.md            built-in image tool rules
│   └── claude-rendering.md            Claude mode
├── examples/
│   ├── image-prompt-templates.md      prompt per image slot
│   ├── svg-templates.md               SVG diagrams for Claude mode
│   ├── output-formats.md              exact reply format
│   ├── sample-run.md                  worked example
│   └── test-cardiac-pain.md           regression test
├── setup/
│   ├── custom-gpt-setup.md
│   └── install-by-link.md
├── feedback/FEEDBACK.md
├── .github/ISSUE_TEMPLATE/feedback.md
└── CHANGELOG.md
```

## Changing it

| Want to change… | Edit |
|---|---|
| Which 4 images a command makes | `knowledge/image-sets.md` |
| Look of images | `knowledge/visual-style-guide.md` |
| Prompt wording | `examples/image-prompt-templates.md` |
| Safety behaviour | `knowledge/safety-rules.md` |
| Commands | `SKILL.md` + `instructions/gpt-instructions.md` + `workflows/commands.md` |

Then bump the version in `SKILL.md`, add a line to `CHANGELOG.md`, and re-upload the changed
files to the Custom GPT. See [`feedback/FEEDBACK.md`](feedback/FEEDBACK.md).

## Known limits
- Image limits depend on the user's ChatGPT plan.
- AI images teach concepts and are not anatomically exact; trust the notes for facts.
