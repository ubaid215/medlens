# Sample Run (reference example)

**User:** *[attaches screenshot of ward notes]* `/medlens`

> Screenshot content (summarised): "68M, 3 days productive cough, fever 38.6 °C, RR 24,
> SpO2 93% RA, BP 118/72, confused? No. Urea 6.1. CXR: right lower lobe consolidation.
> Impression: CAP. Plan: abx, O2 PRN."

---

### 🩺 MedLens — Topic Card
**Source:** Clinical notes
**Mode:** Doctor (auto-detected — type /student to switch)

| | |
|---|---|
| **Condition(s)** | Community-acquired pneumonia (CAP) · differentials: aspiration, PE, heart failure |
| **Organ system** | Respiratory — right lower lobe, alveoli |
| **Key findings** | Productive cough · fever 38.6 °C · RR 24 · SpO2 93% · RLL consolidation on CXR |
| **Treatments mentioned** | Antibiotics, oxygen as needed |
| **Red flags** | None currently (no shock, SpO2 ≥ 92%). CURB-65 = 1 (age ≥ 65) from the values shown |

*Assumptions:* no confusion (stated), urea 6.1 mmol/L (not > 7). Tell me if this is wrong.

---

### 🗺️ Visual Plan — 13 images · 4 batches

| # | Category | Image | Style |
|---|---|---|---|
| 1 | Anatomy | Lungs & bronchial tree, RLL highlighted | 3D |
| 2 | Physiology | Normal alveolar gas exchange | 3D + arrows |
| 3 | Causes & risks | Common CAP pathogens + risk factors | Infographic |
| 4 | Pathogenesis | Aspiration → alveolar invasion → inflammation → consolidation | 4 panels |
| 5 | Pathology | Normal vs consolidated lobe + exudate-filled alveoli inset | 3D split |
| 6 | Clinical features | Body map: cough, fever, tachypnoea, crackles, dullness | Body map |
| 7 | Investigations | CXR RLL consolidation · bloods (CRP ↑, WCC ↑) · SpO2 | Panels |
| 8 | Diagnosis flow | Suspected CAP → CXR → CURB-65 → severity → setting of care | Flowchart |
| 9 | Differentials | CAP vs aspiration vs PE vs heart failure | Grid |
| 10 | Pharmacology | Penicillin (amoxicillin): cell-wall synthesis inhibition, why first-line in low severity | 3D mechanism |
| 11 | Non-drug management | Sit upright, O2 to target sats, fluids, early mobilisation | Realistic ward scene |
| 12 | Complications | Parapneumonic effusion, empyema, sepsis, abscess | 3D body |
| 13 | Follow-up & prevention + patient advice | 48–72 h review, 6-week CXR if indicated, vaccination, smoking cessation | Timeline |

Generating images 1–4 now…

---

*[Image 1 generated]*

**1. Respiratory anatomy — right lower lobe** · *Anatomy*
- Right lung has 3 lobes; RLL is the commonest site for aspiration-related consolidation
  (more vertical right main bronchus).
- Segmental bronchi → bronchioles → alveoli.
- RLL consolidation: dullness and crackles posteriorly at the right base.
📚 *Standard anatomy*

*[Images 2–4 …]*

✅ Images 1–4 of 13 done.
Type **next** for 5–8 · `/redo <n> <feedback>` to fix one · `/only <n…>` to jump.

---

### Example prompt used for image 10
```
3D medical illustration of how penicillin-class antibiotics (e.g. amoxicillin) work in
community-acquired pneumonia. Show a Streptococcus pneumoniae bacterium in an alveolus with
blue drug molecules binding to "Penicillin-binding proteins" in the cell wall, and the
effect: "Cell wall breaks down" (arrows to a lysing bacterium). Side box: "Why first-line:
covers pneumococcus, low severity". Labels: "Amoxicillin", "Penicillin-binding proteins",
"Cell wall", "Bacterial lysis". No doses. Title: "Penicillins: mechanism".
Landscape 3:2. STYLE: Professional medical education illustration, high detail, clean
composition, soft neutral background, consistent colour palette (normal green, disease red,
treatment blue, warning orange, tests purple), sharp legible labels in clean sans-serif font.
Small footer text "MedLens · Educational use". EXCLUDE: extra text, paragraphs, doses,
watermarks, patient identifiers, graphic gore.
```

Caption for image 10 (Doctor mode):
- **Why chosen:** low-severity CAP (CURB-65 0–1) — amoxicillin covers *S. pneumoniae*, the
  commonest cause (NICE NG138 recommends amoxicillin first-line for low severity).
- Moderate/high severity: guideline adds a macrolide ± broader β-lactam — check current
  NICE NG138 / BTS / local antimicrobial policy.
- **Watch for:** penicillin allergy (use guideline alternative), rash, diarrhoea, *C. difficile*.
- **Monitoring:** clinical response at 48–72 h; review if not improving.
- Typical adult dose: per NICE NG138 / BNF — verify with local formulary; adjust for renal
  function and interactions.
📚 *NICE NG138 (Pneumonia, community-acquired: antimicrobial prescribing) — check latest version*
