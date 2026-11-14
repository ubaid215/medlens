# MedLens 🩺

**Medical screenshot → detailed, high-resolution medical infographic sheets, from anatomy to treatment.**

Upload a screenshot of a textbook page, lecture slide, clinical notes or a report. Type a
command and MedLens clarifies the topic with as many detailed, readable infographic sheets
as it needs — 3D anatomy atlases, step cards, exam-technique photo panels, OPD drug cards
and surgical step-by-step sheets.

Built for **everyone in medicine**: students, doctors, exam candidates, nurses and patients. Runs inside ChatGPT with its built-in image
generation — **no API key needed**.

> ⚠️ Educational use only. Not a diagnostic tool and not a substitute for clinical judgement,
> local guidelines or a prescriber.

---

## Use

| Command | Covers |
|---|---|
| `/anatomy` | **Pure gross anatomy** — one ultra-detailed atlas plate of the organ in your screenshot, richly labelled |
| `/visualize` | **Detailed overview poster** — one dark-navy poster explaining the whole topic: central 3D illustration + information cards |
| `/medlens` | **Anatomy & origin** — structures, root cause, where the disease starts, first symptoms; recommends your next command |
| `/pathology` | **The disease in depth** — causes, mechanism, gross & microscopic changes, types, complications |
| `/tests` | **Clinical examination & diagnosis** — history, exam signs, labs, imaging, scores, differentials |
| `/clinical` | **Management** — automatically **OPD** (drug cards: which drug, how it works, why chosen, side effects, avoid in, monitor + lifestyle & follow-up) or **Surgical** (pre-op → step-by-step operation → post-op). Force with `/clinical opd` or `/clinical surgical` |
| `/student` `/doctor` `/exam` `/patient` | Choose the level; student/exam use a study-notebook look, exam adds MCQs/viva questions |
| `/redo 2` | Remake sheet 2 (`/redo 2 less text`) |
| `/help` | Command list |

MedLens decides how many sheets each topic needs. If ChatGPT stops mid-way, type `continue`.

Start with `/medlens`; it tells you which command to use next. Add a focus if you like:
`/clinical surgical laparoscopic`, `/pathology histology`.

---

## Install

### Option A — Custom GPT (recommended)
Follow [`setup/custom-gpt-setup.md`](setup/custom-gpt-setup.md): paste
`instructions/gpt-instructions.md` into **Configure → Instructions**, upload the knowledge
files, turn on **Image Generation**, turn **Web Search off**.

### Option B — Try it in one ChatGPT chat
Paste the instructions as your first message — see [`setup/install-by-link.md`](setup/install-by-link.md).
Pasting a GitHub link is not recommended: it switches ChatGPT to web search, which gives
text articles instead of sheets.

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
│   ├── visual-style-guide.md          sheet layouts, readability, colours
│   └── safety-rules.md                medical guardrails
├── workflows/
│   ├── full-run.md                    steps for any command
│   └── commands.md                    command details
├── tools/
│   ├── image-generation.md            built-in image tool rules
│   └── claude-rendering.md            Claude mode
├── examples/
│   ├── master-prompts.md              full prompts for /anatomy and /visualize
│   ├── image-prompt-templates.md      prompt per layout (L1–L7)
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
