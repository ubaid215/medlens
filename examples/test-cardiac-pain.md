# Regression Test — "Cardiac Pain" clinical notes page

Use after any change. Source: textbook "Clinical Notes — Cardiac Pain" box.

## Facts the images must respect
1. Afferents ascend via **cardiac branches of the sympathetic trunk**.
2. Enter the cord via **posterior roots of the upper four thoracic nerves (T1–T4)**.
3. Referred to skin of the upper four intercostal nerves + **intercostobrachial nerve (T2)**
   → **medial upper arm**; sometimes **neck and jaw**.
4. Pain ranges from severe crushing to mild discomfort.
5. **Inferior-wall/diaphragmatic MI → T7–T9 → epigastrium.** Separate from fact 2.
6. Acute oesophagitis can mimic MI.

## What each command should cover (count decided by the model)

| Command | Must include |
|---|---|
| `/medlens` | Cardiac sensory nerves → sympathetic trunk → T1–T4; root cause (ischaemia → metabolites stimulate nerve endings); starting point (ischaemic myocardium / coronary plaque); convergence in dorsal horn; referred areas (chest, medial arm T2, neck, jaw); inferior-wall MI → T7–T9 epigastrium. Next: `/pathology` for acute coronary syndrome (emergency → `/tests` first acceptable) |
| `/pathology` | Risk factors, plaque → rupture → thrombus → ischaemia → infarction, healthy vs blocked artery, histology timeline of infarct, types (STEMI/NSTEMI/unstable angina), complications |
| `/tests` | History of chest pain, examination, ECG changes, troponin, risk scores, differentials (oesophagitis, PE, dissection), diagnosis path |
| `/clinical` | Auto: emergency/medical + procedure (both): antiplatelets (why), anticoagulation, primary PCI, secondary prevention; ends "Also available: /clinical surgical" (CABG) or similar |

## Pass criteria
- [ ] `/help` shows the exact v3 welcome text
- [ ] Topic line shows command name, image count and mode
- [ ] Image count fits the topic (not fixed); every "must include" point is covered
- [ ] `/medlens` ends with a recommended next command
- [ ] Each image is one idea — no poster layout, text boxes, legends or logos
- [ ] No image says "T2–T9", "T1–T5", or puts chest/arm pain at T7–T9
- [ ] No main picture repeated across commands
- [ ] `/clinical` notes say which drug/procedure and why; guideline named; safety line at end
- [ ] `/exam` adds MCQ/viva questions with answers at the end
- [ ] No doses inside any image

## Earlier failures this test catches
- v1.1: posters repeating heart + spine + patient; wrong levels (T2–T9, T1–T5).
- v1.2: treatment images were dense posters with doses ("Aspirin 300mg") and a third-party logo.
