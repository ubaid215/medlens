# Image Prompt Templates

Fill the `[brackets]`. Always append the **global style block** and **exclude line**:

> **STYLE:** Professional medical education illustration, high detail, clean composition,
> soft neutral background, consistent colour palette (normal green, disease red, treatment
> blue, warning orange, tests purple), sharp legible labels in clean sans-serif font.
> Small footer text "MedLens · Educational use".
> **EXCLUDE:** extra text, paragraphs, doses, watermarks, patient identifiers, graphic gore.

---

### 0. Urgent Action (red flags only)
```
Bold medical emergency infographic for "[CONDITION]". Red banner at top with text
"URGENT: [CONDITION]". Below, [3–5] large numbered action cards with icons:
"[Action 1]", "[Action 2]", "[Action 3]", "[Action 4]". Small 3D inset of the affected
organ ([organ]) with the critical lesion highlighted in red. Landscape 3:2. STYLE. EXCLUDE.
```

### 1. Normal anatomy
```
Photorealistic 3D anatomical render of a healthy [ORGAN/REGION], [cutaway | cross-section |
exploded] view from [anterior | lateral | superior] angle, soft studio lighting, light-grey
gradient background. Realistic tissue colours. Labels (exact text): "[s1]", "[s2]", "[s3]",
"[s4]", "[s5]". Title: "Normal [organ] anatomy". Landscape 3:2. STYLE. EXCLUDE.
```

### 2. Normal physiology
```
3D medical illustration of normal [PROCESS] in the [ORGAN]. Show [flow/conduction/transport]
as smooth green arrows following the correct direction: [path in order]. Labels: "[…]".
Title: "How the [organ] normally works". Landscape 3:2. STYLE. EXCLUDE.
```

### 3. Causes & risk factors
```
Clean medical infographic. Centre: 3D [ORGAN] showing early [DISEASE]. Around it, [5–7]
icons with short labels: "[Risk 1]", "[Risk 2]", … connected by thin lines. Modifiable
risks in orange, non-modifiable in grey. Title: "[DISEASE]: causes & risk factors".
Landscape 3:2. STYLE. EXCLUDE.
```

### 4. Pathogenesis
```
Sequential medical illustration in [3–5] panels left to right, numbered circles 1–[n].
Panel 1: "[stage 1]" — [what is shown]. Panel 2: "[stage 2]" — […]. Panel 3: … .
Cellular/tissue level 3D rendering, arrows between panels, disease changes in red.
Title: "How [DISEASE] develops". Landscape 3:2. STYLE. EXCLUDE.
```

### 5. Pathology (healthy vs diseased)
```
Split-view 3D medical illustration. Left half "Normal": healthy [ORGAN/TISSUE]. Right half
"[DISEASE]": [specific gross changes]. Thin vertical divider. Circular magnified inset on the
right showing microscopic [histology finding]. Labels: "[…]". Landscape 3:2. STYLE. EXCLUDE.
```

### 6. Clinical features
```
Semi-transparent 3D human figure, [anterior] view, neutral pose, with [organs] visible.
Callout lines from body sites to labels: "[symptom/sign 1]" at [site], "[…]" at [site] …
(max 8). Symptoms in red, signs in orange. Title: "[DISEASE]: clinical features".
Portrait 2:3. STYLE. EXCLUDE.
```

### 7. Investigations
```
Clean medical panel layout with [2–4] panels: [e.g. "ECG" showing (finding) | "Chest X-ray"
showing (finding) | "Blood tests" card with arrows ↑/↓ next to "(test)"]. Abnormal findings
highlighted in purple outlines. Labels: "[…]". Title: "[DISEASE]: key investigations".
Landscape 3:2. STYLE. EXCLUDE.
```

### 8. Diagnosis flow
```
Flat vector medical flowchart, white background, rounded boxes and decision diamonds.
Start: "[presentation]" → "[test/criterion]" → diamond "[question]?" → Yes: "[…]" /
No: "[…]" → … → "[diagnosis]". Max 8 boxes. Title: "Diagnosing [DISEASE]".
Portrait 2:3. STYLE. EXCLUDE.
```

### 9. Non-drug management
```
[Realistic photographic scene | clean icon infographic] showing non-drug management of
[DISEASE]: "[measure 1]", "[measure 2]", "[measure 3]", "[measure 4]". [Scene: e.g. nurse
positioning patient upright in a modern ward]. Title: "Non-drug management".
Landscape 3:2. STYLE. EXCLUDE.
```

### 10. Pharmacology (mechanism + why chosen)
```
3D medical illustration of how [DRUG CLASS] (e.g. [example drug]) works in [DISEASE].
Show the [target organ/cell/receptor] with blue drug molecules binding to "[target]" and
the effect: "[effect]" (arrows). Side box: "Why first-line: [reason in ≤ 6 words]".
Labels: "[drug class]", "[target]", "[effect]". No doses.
Title: "[DRUG CLASS]: mechanism". Landscape 3:2. STYLE. EXCLUDE.
```

### 10x. Treatment ladder
```
Flat vector step ladder, [3–5] steps bottom to top: Step 1 "[therapy]", Step 2 "[…]", …
Each step a blue box; escalation arrow on the side "if not controlled". Guideline tag at
bottom: "[e.g. NICE NG136]". No doses. Portrait 2:3. STYLE. EXCLUDE.
```

### 11. Procedure / surgery
```
Photorealistic scene in a modern [operating theatre | procedure room | ICU | clinic]:
[clinician role(s)] performing [PROCEDURE] on a [draped] patient, correct sterile attire,
equipment: [list]. Non-graphic, surgical field shown cleanly. [Optional: 3–4 numbered inset
panels of key steps "[step]"]. Title: "[PROCEDURE]". Landscape 3:2. STYLE. EXCLUDE.
```

### 12. Complications
```
3D medical illustration of [ORGAN/BODY] showing complications of untreated [DISEASE]:
callouts in orange "[complication 1]", "[complication 2]", … (max 6) at the correct sites.
Title: "[DISEASE]: complications". Landscape 3:2. STYLE. EXCLUDE.
```

### 13. Follow-up & prevention
```
Horizontal medical timeline infographic: "Diagnosis" → "[time]: [monitor/test]" →
"[time]: [review]" → "Long-term: [target]". Prevention icons below: "[…]".
Title: "Follow-up & prevention". Landscape 3:2. STYLE. EXCLUDE.
```

### 14. Patient counselling
```
Warm friendly semi-flat illustration for patients. Simple drawing of [organ] with a smiling
clinician explaining. 4 large icon cards with simple words: "[What it is]", "[What helps]",
"[What you can do]", "[Get help if…]". Title: "Understanding [condition]". Large readable
text. Landscape 3:2. STYLE. EXCLUDE.
```

### Extra — Differential diagnosis
```
Clean comparison grid, [3–4] columns: "[Dx 1]", "[Dx 2]", "[Dx 3]". Each column: small 3D
organ icon showing the key lesion + 2 short distinguishing labels. Title: "Differentials".
Landscape 3:2. STYLE. EXCLUDE.
```

---

## Mode modifiers (add to the prompt)
- **Quiz:** "Replace all label text with numbered circles ①②③…; no words except the title."
- **Patient:** "Simple friendly style, large text, everyday words, max 5 labels."
- **Doctor:** "Denser layout allowed: up to 4 panels; include score/criteria names."
- **Redo with feedback:** start with "Revise previous image: [feedback]." then the full prompt.
