# MedLens 🩺

**Medical screenshot → clear medical images, from anatomy to treatment.**

Send a screenshot of a textbook page, lecture slide, clinical notes or a report. Type a
command and MedLens makes as many clear images as the topic needs, one idea each, with
short notes.

Built for **everyone in medicine**: students, doctors, exam candidates, nurses and patients. Runs inside ChatGPT with its built-in image
generation — **no API key needed**.

> ⚠️ Educational use only. Not a diagnostic tool and not a substitute for clinical judgement,
> local guidelines or a prescriber.

---

## Use

| Command | Covers |
|---|---|
| `/medlens` | **Anatomy & origin** — structures, root cause, where the disease starts, first symptoms; recommends your next command |
| `/pathology` | **The disease in depth** — causes, mechanism, gross & microscopic changes, types, complications |
| `/tests` | **Clinical examination & diagnosis** — history, exam signs, labs, imaging, scores, differentials |
| `/clinical` | **Management** — automatically **OPD** (which medicine, how it works, why) or **Surgical** (pre-op → operation → post-op). Force with `/clinical opd` or `/clinical surgical` |
| `/student` `/doctor` `/exam` `/patient` | Choose the level of explanation (exam mode adds MCQs/viva questions) |
| `/redo 2` | Remake image 2 (`/redo 2 bigger labels`) |
| `/help` | Command list |

MedLens decides how many images each topic needs. If ChatGPT stops mid-way, type `continue`.

Start with `/medlens`; it tells you which command to use next. Add a focus if you like:
`/clinical surgical laparoscopic`, `/pathology histology`.

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
**Claude mode**: diagrams (flows, body maps, mechanisms, ECGs, treatment plans, surgical workflows) are drawn
directly; 3D anatomy, examination and operating-theatre scenes come as a labelled sketch plus a prompt
to paste into any image generator.

---

## Folder structure

```
medlens/
├── SKILL.md                         Instructions (entry point)
├── instructions/gpt-instructions.md Instructions for the Custom GPT (< 8000 chars)
├── knowledge/
│   ├── command-coverage.md            what each command covers, OPD vs surgical
│   ├── modes.md                       student / doctor / exam / patient
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
| What a command covers | `knowledge/command-coverage.md` |
| Audience wording | `knowledge/modes.md` |
| Look of images | `knowledge/visual-style-guide.md` |
| Prompt wording | `examples/image-prompt-templates.md` |
| Safety behaviour | `knowledge/safety-rules.md` |
| Commands | `SKILL.md` + `instructions/gpt-instructions.md` + `workflows/commands.md` |

Then bump the version in `SKILL.md`, add a line to `CHANGELOG.md`, and re-upload the changed
files to the Custom GPT. See [`feedback/FEEDBACK.md`](feedback/FEEDBACK.md).

## Known limits
- Image limits depend on the user's ChatGPT plan.
- AI images teach concepts and are not anatomically exact; trust the notes for facts.
