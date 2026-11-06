# Feedback → Improvement Loop

## Collecting feedback
- Users open a GitHub issue with the **Feedback** template (`.github/ISSUE_TEMPLATE/feedback.md`).
- Ask testers to include: the command, screenshot type (no patient data!), image number,
  what was wrong, what they expected.

## Triage — where each kind of feedback goes

| Feedback | File to edit |
|---|---|
| "A command misses something" / "wrong OPD vs surgical choice" | `knowledge/command-coverage.md` |
| "Wording too hard / too simple" | `knowledge/modes.md` |
| "Images look inconsistent / too cartoonish / wrong colours" | `knowledge/visual-style-guide.md` |
| "Labels misspelled / cluttered" | `knowledge/visual-style-guide.md` (labels) + relevant template |
| "This image type is always wrong" | `examples/image-prompt-templates.md` |
| "Notes too long / too short" | `examples/output-formats.md` |
| "Wrong or outdated treatment" | `knowledge/safety-rules.md` (guideline rules) — and verify with the guideline |
| "Command doesn't work as expected" | `workflows/commands.md` + `SKILL.md` + `instructions/gpt-instructions.md` |
| "Stops / image fails" | `tools/image-generation.md` |

## Release steps
1. Make the edit on a branch; keep `SKILL.md` and `instructions/gpt-instructions.md` in sync.
2. Check `instructions/gpt-instructions.md` stays **under 8,000 characters**.
3. Bump `version` in `SKILL.md` (patch = wording, minor = new image type/command,
   major = changed behaviour).
4. Add an entry to `CHANGELOG.md`.
5. Re-run the 5 tests in `setup/custom-gpt-setup.md` §5.
6. Merge, then update the Custom GPT (re-upload changed knowledge files / re-paste instructions).

## Medical content changes
Any change to treatment, drug or red-flag content should be reviewed by a qualified clinician
and cite the guideline used in the commit message.
