# Custom GPT Setup (ChatGPT)

Requires a ChatGPT plan that can create GPTs.

## 1. Create
ChatGPT → **Explore GPTs** → **+ Create** → switch to the **Configure** tab.

> ⚠️ **Do not use the "Create" chat tab** (where you describe the GPT in conversation).
> The GPT Builder rewrites the instructions in its own words and MedLens's rules are lost —
> you get posters, repeated images and missing topics. Paste everything in **Configure**.
> If you used the Create chat before, delete everything in the Instructions box and paste
> `gpt-instructions.md` again.

## 2. Fill the fields

**Name**
```
MedLens
```

**Description**
```
Send a medical screenshot — get every image you need to understand it: 3D anatomy, pathology, clinical features, investigations, treatment, drug mechanisms and real clinical scenes. For medical students & doctors. Educational use only.
```

**Instructions**
Paste the entire content of [`instructions/gpt-instructions.md`](../instructions/gpt-instructions.md)
— from "You are MedLens v3" to the last line, nothing added, nothing summarised.
(It is under ChatGPT's 8,000-character limit.)

**Conversation starters**
```
/medlens — anatomy, root cause & where the disease starts
/pathology — the disease in depth
/tests — clinical examination & diagnosis
/clinical — management (OPD or surgical)
```

**Knowledge** — upload these files:
```
knowledge/command-coverage.md
knowledge/modes.md
knowledge/visual-style-guide.md
knowledge/safety-rules.md
workflows/full-run.md
workflows/commands.md
tools/image-generation.md
examples/image-prompt-templates.md
examples/output-formats.md
examples/sample-run.md
examples/test-cardiac-pain.md
```
When updating, **delete the old copies first**, then upload the new files.

**Capabilities**
- ✅ Image Generation — **required**
- ✅ Web Search — optional (helps check the latest guideline versions)
- ⬜ Code Interpreter — not needed
- ⬜ Canvas — not needed

**Actions** — none (no external APIs).

## 3. Profile picture
Use the image generator in the builder with:
```
Minimal app icon: a stylised lens over a 3D heart and lungs outline, teal and white, flat, rounded square.
```

## 4. Save & share
**Create / Update** → choose **Anyone with the link** (or GPT Store). Copy the link into the
repository README so users can open it.

## 5. Test before sharing
1. **Type `/help` in a new chat.** The reply must start with "🩺 MedLens v3 ready."
   If not, the instructions were not pasted correctly — redo step 2 in **Configure**.
2. Send a screenshot with `/medlens` → topic line with image count, anatomy + root cause +
   starting point images (no posters), and a recommended next command.
3. `/clinical` on a surgical topic (e.g. appendicitis) → Surgical pathway: pre-op,
   operation steps, post-op. On a medical topic (e.g. hypertension) → OPD pathway with
   which medicine and why. No doses inside images.
4. `/exam` → MCQ/viva questions with answers at the end.
5. `/redo 2 fewer labels` → only image 2 changes.
6. Run `examples/test-cardiac-pain.md` and tick its pass criteria.

If you used an older version: delete **all** old Knowledge files (including
`image-sets.md` and `coverage-checklist.md`) before uploading the new ones.

## 6. Updating after feedback
Edit the file in GitHub → re-upload **only the changed file(s)** in Knowledge (delete the old
copy first) or re-paste Instructions → **Update**. Note the change in `CHANGELOG.md`.
