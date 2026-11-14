# Custom GPT Setup (ChatGPT)

Requires a ChatGPT plan that can create GPTs.

## 1. Create
ChatGPT → **Explore GPTs** → **+ Create** → switch to the **Configure** tab.

> ⚠️ **Do not use the "Create" chat tab** (where you describe the GPT in conversation).
> The GPT Builder rewrites the instructions in its own words and MedLens's rules are lost —
> you get text articles, web images and missing topics. Paste everything in **Configure**.
> If you used the Create chat before, delete everything in the Instructions box and paste
> `gpt-instructions.md` again.

## 2. Fill the fields

**Name**
```
MedLens
```

**Description**
```
Upload a medical screenshot — get detailed, high-resolution infographic sheets: 3D anatomy, root cause, pathology, examination & diagnosis, OPD drug cards and surgical workflows. For students, doctors & exam prep. Educational use only.
```

**Instructions**
Paste the entire content of [`instructions/gpt-instructions.md`](../instructions/gpt-instructions.md)
— from "You are MedLens v4.3" to the last line, nothing added, nothing summarised.
(It is under ChatGPT's 8,000-character limit.)

**Conversation starters**
```
/anatomy — detailed gross anatomy plate
/visualize — full overview poster of my topic
/medlens — explain my whole topic in sheets
/clinical — OPD drugs or surgery
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
examples/master-prompts.md
examples/output-formats.md
examples/sample-run.md
examples/test-cardiac-pain.md
```
When updating, **delete the old copies first**, then upload the new files.

**Capabilities**
- ✅ Image Generation — **required**
- ⬜ Web Search — **OFF** (when on, ChatGPT answers with web thumbnails and text articles
  instead of generating sheets, and takes facts from the web instead of your screenshot)
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
1. **Type `/help` in a new chat.** The reply must start with "🩺 MedLens v4.3 ready."
   If not, the instructions were not pasted correctly — redo step 2 in **Configure**.
2. Upload a screenshot with `/medlens` → topic line, then **generated sheets straight
   away** (no text article, no web thumbnails), detailed and readable, and a recommended
   next command.
2a. Upload a screenshot with **no command** → no images, only the command list.
2b. `/anatomy` → **exactly one image**: a white atlas plate titled "DETAILED ANATOMY OF THE HUMAN …" with
   20–30 correctly spelled labels, no disease content. `/visualize` → one dark-navy
   poster with a central 3D hero and 6–10 info cards, no doses or lab values.
3. `/clinical` on a medical topic (e.g. hypertension) → OPD sheets with **drug cards**
   (Use · How · Why · Side effects · Avoid in · Monitor). On a surgical topic (e.g.
   appendicitis) → indications, pre-op, step-by-step operation, post-op.
4. `/student` → notebook-style sheets, no doses. `/exam` → adds MCQ/viva questions.
5. Zoom into each sheet: spelling correct, no logos, no duplicated sections.
6. `/redo 2 less text` → only sheet 2 changes.
7. Run `examples/test-cardiac-pain.md` and tick its pass criteria.

If you used an older version: delete **all** old Knowledge files before uploading the new ones.

## 6. Updating after feedback
Edit the file in GitHub → re-upload **only the changed file(s)** in Knowledge (delete the old
copy first) or re-paste Instructions → **Update**. Note the change in `CHANGELOG.md`.
