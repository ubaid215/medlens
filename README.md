# MedLens 🩺

**Medical screenshot → complete visual explanation.**

Share a screenshot of a textbook page, lecture slide, clinical notes, lab report or imaging
report. MedLens reads it, finds every topic in it, and generates a **full set of educational
images**: 3D anatomy, pathology, clinical features, investigations, diagnosis flow, treatment,
drug mechanisms, procedures, complications and patient counselling.

Built for **medical students** and **doctors**. Runs inside ChatGPT with its built-in image
generation — **no API key needed**.

> ⚠️ Educational use only. Not a diagnostic tool and not a substitute for clinical judgement,
> local guidelines or a prescriber.

---

## Install

### Option A — Custom GPT (recommended, most reliable)
1. In ChatGPT go to **Explore GPTs → Create → Configure**.
2. Follow [`setup/custom-gpt-setup.md`](setup/custom-gpt-setup.md):
   paste `instructions/gpt-instructions.md` into **Instructions**,
   upload every file in `knowledge/`, `workflows/`, `tools/` and `examples/` as **Knowledge**,
   turn on **Image Generation**.
3. Save. Share the GPT link with users.

### Option B — Paste the GitHub link into any ChatGPT chat
Copy the prompt from [`setup/install-by-link.md`](setup/install-by-link.md), replace
`<your-username>` with your GitHub username, and paste it into a new chat.
ChatGPT reads the skill files from GitHub and follows them **for that chat**.
(Needs web access in ChatGPT. Option A is more reliable because the files are always loaded.)

### Option C — Platforms that support Agent Skills (`SKILL.md`)
Upload the whole `medlens/` folder (or a zip of it) as a skill. `SKILL.md` is the entry point.

---

## Use

Attach a screenshot and type:

| Command | What it does |
|---|---|
| `/medlens` | Full run: topic card → visual plan → all images (in batches) |
| `/plan` | Show the plan only |
| `/next` | Next batch of images |
| `/only 3 7 10` | Only those images |
| `/redo 5` | Regenerate image 5 (add feedback after the number) |
| `/student` · `/doctor` · `/quiz` · `/patient` | Switch mode |
| `/help` | Command list |

---

## Folder structure

```
medlens/
├── SKILL.md                         1. Instructions (entry point)
├── instructions/gpt-instructions.md 1. Instructions (Custom GPT version, < 8000 chars)
├── knowledge/                       2. Knowledge
│   ├── coverage-checklist.md          which images to make
│   ├── visual-style-guide.md          how images look
│   ├── safety-rules.md                medical guardrails + red flags
│   └── modes.md                       student / doctor / quiz / patient
├── workflows/                       3. Workflows
│   ├── full-run.md                    the /medlens pipeline
│   └── commands.md                    every command in detail
├── tools/                           4. Tools
│   └── image-generation.md            built-in image tool, batching, limits
├── examples/                        5. Examples & output formats
│   ├── image-prompt-templates.md      a template per image category
│   ├── output-formats.md              topic card, plan, captions, summary
│   └── sample-run.md                  full worked example
├── setup/
│   ├── custom-gpt-setup.md
│   └── install-by-link.md
├── feedback/FEEDBACK.md             how user feedback becomes changes
├── .github/ISSUE_TEMPLATE/feedback.md
└── CHANGELOG.md
```

---

## Customising & improving from feedback

| Want to change… | Edit |
|---|---|
| Which images get made | `knowledge/coverage-checklist.md` |
| Look of images | `knowledge/visual-style-guide.md` |
| Prompt wording per image type | `examples/image-prompt-templates.md` |
| Safety behaviour | `knowledge/safety-rules.md` |
| Commands | `workflows/commands.md` + `SKILL.md` + `instructions/gpt-instructions.md` |

Process: collect feedback (GitHub issue template) → edit the file → bump the version in
`SKILL.md` → add a line to `CHANGELOG.md` → re-upload changed files to the Custom GPT.
See [`feedback/FEEDBACK.md`](feedback/FEEDBACK.md).

## Known limits
- ChatGPT creates images one at a time; a 12-image run takes a few minutes and a few `/next`.
- Image limits depend on the user's ChatGPT plan; free plans may stop mid-run.
- AI images teach concepts and are not anatomically exact. Trust the caption text for facts.
