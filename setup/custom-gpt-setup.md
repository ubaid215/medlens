# Custom GPT Setup (ChatGPT)

Requires a ChatGPT plan that can create GPTs.

## 1. Create
ChatGPT → **Explore GPTs** → **+ Create** → switch to the **Configure** tab.

> ⚠️ **Do not use the "Create" chat tab** (where you describe the GPT in conversation).
> The GPT Builder rewrites the instructions in its own words and MedLens's rules are lost —
> you get posters, repeated images and only ~4 images. Paste everything in **Configure**.
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
— from "You are MedLens v1.2" to the last line, nothing added, nothing summarised.
(It is under ChatGPT's 8,000-character limit.)

**Conversation starters**
```
/medlens — attach a screenshot to explain it fully in images
/plan — show which images you would make for my screenshot
/student — explain my lecture slide visually
/doctor — visualise these clinical notes with treatment pathway
```

**Knowledge** — upload these files:
```
knowledge/coverage-checklist.md
knowledge/visual-style-guide.md
knowledge/safety-rules.md
knowledge/modes.md
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
0. **Type `/help` in a new chat.** The reply must start with
   "🩺 MedLens v1.2 ready." If it doesn't, the instructions were not pasted correctly —
   redo step 2 in **Configure**.
1. Send a lecture slide screenshot with no command → expect Fact Sheet, Topic Card, plan of 8+
   images (with "➕ beyond source" clinical rows), batch of 4, Student mode, single-concept
   images (no posters).
1b. Run the regression test in `examples/test-cardiac-pain.md` and tick its pass criteria.
2. Send clinical notes with `/doctor` → expect guideline names, no doses inside images.
3. Send an ECG showing ST elevation → expect the URGENT image first.
4. `/quiz` → numbered labels, answers at the end.
5. `/redo 2 fewer labels` → only image 2 changes.

## 6. Updating after feedback
Edit the file in GitHub → re-upload **only the changed file(s)** in Knowledge (delete the old
copy first) or re-paste Instructions → **Update**. Note the change in `CHANGELOG.md`.
