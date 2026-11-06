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

## Expected images

| Command | 1 | 2 | 3 | 4 |
|---|---|---|---|---|
| `/medlens` | Heart's pain nerves → sympathetic trunk, T1–T4 | Convergence in dorsal horn | Body map: chest, medial arm, neck, jaw | Inferior-wall MI → T7–T9 epigastrium |
| `/pathology` | Risk factors for coronary disease | Plaque → rupture → clot → ischaemia | Healthy vs blocked coronary artery | Complications (arrhythmia, heart failure, rupture) |
| `/tests` | Bedside signs (sweating, pallor) | ECG ST elevation | Troponin rise | Chest pain diagnosis flow |
| `/treatment` | Plan: STEMI vs NSTE-ACS | Antiplatelets mechanism | Primary PCI cath lab | Recovery & prevention cards |

## Pass criteria
- [ ] `/help` shows the exact v2 welcome text
- [ ] Every command returns **exactly 4** images
- [ ] Reply has only: topic line, 4 images with 2–4 bullet notes, `Next:` line
- [ ] Each image is one idea — no poster layout, no text boxes, no legends, no brand titles
- [ ] No image says "T2–T9", "T1–T5", or puts chest/arm pain at T7–T9
- [ ] Whole heart / spine / patient holding chest is the main subject at most once
- [ ] `/treatment` notes say which drug or procedure and why; guideline named
- [ ] No doses inside any image

## Earlier failures this test catches
- v1.1: only 4 planned images, all posters repeating heart + spine + patient; wrong levels.
- v1.2: `/treatment` images were dense posters with doses ("Aspirin 300mg", "Ticagrelor
  180mg"), legends and a third-party logo.
