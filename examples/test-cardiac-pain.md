# Regression Test — "Cardiac Pain" clinical notes page

Use this to check MedLens after any change. Source: a textbook "Clinical Notes — Cardiac
Pain" box (anatomy-only text, no treatment). Version 1.1 failed this test (see bottom).

## Expected Fact Sheet
1. Oxygen deficiency and accumulated metabolites stimulate sensory nerve endings in the
   myocardium → pain in acute myocardial ischaemia.
2. Afferent fibres ascend through the **cardiac branches of the sympathetic trunk**.
3. They enter the spinal cord through the **posterior roots of the upper four thoracic
   nerves (T1–T4)**.
4. Pain ranges from severe crushing pain to mild discomfort.
5. Pain is referred to skin supplied by the **upper four intercostal nerves** and the
   **intercostobrachial nerve (T2)**.
6. The intercostobrachial nerve communicates with the **medial cutaneous nerve of the arm**
   → skin of the **medial upper arm**.
7. Spread within the CNS → pain sometimes felt in the **neck and jaw**.
8. **Inferior-wall / diaphragmatic MI** → afferents enter **T7–T9** → discomfort in the
   **epigastrium** (T7–T9 dermatomes). *Separate from fact 3.*
9. Heart and thoracic oesophagus probably share afferent pathways → **acute oesophagitis can
   mimic MI**.

## Expected Visual Plan (Student mode, ≈ 15 images)

| # | Category | One concept | New element shown |
|---|---|---|---|
| 1 | Anatomy | Cardiac sensory innervation | 3D heart + cardiac branches → sympathetic trunk |
| 2 | Pathogenesis | Ischaemia → metabolites → nerve endings | Microscopic myocardium close-up |
| 3 | Physiology | Afferent route into the cord | Cord cross-section, posterior roots T1–T4, dorsal horn |
| 4 | Clinical features | Referred pain T1–T4 | Anterior chest dermatome map T1–T4 |
| 5 | Anatomy | Medial arm pain | Intercostobrachial (T2) + medial cutaneous nerve of arm |
| 6 | Physiology | Neck & jaw pain via CNS spread | Neck/jaw body map with convergence schematic |
| 7 | Pathology | Inferior-wall MI → epigastrium | Inferior wall inset + T7–T9 epigastric dermatomes |
| 8 | Clinical features | Pain character spectrum | Severity scale crushing → mild discomfort |
| 9 | Differentials | Oesophagitis vs MI | Oesophagus vs heart comparison |
| 10 | ➕ Investigations | ECG + troponin | ECG strip with ST changes, troponin curve |
| 11 | ➕ Diagnosis flow | Chest pain pathway | Flowchart: ECG → STEMI / NSTE-ACS / non-cardiac |
| 12 | ➕ Pharmacology | Antiplatelets | Platelet with aspirin / P2Y12 target |
| 13 | ➕ Pharmacology | Nitrates | Venodilation → reduced preload |
| 14 | ➕ Procedure | Reperfusion | Cath lab primary PCI scene |
| 15 | Patient counselling | When to call emergency help | 4 icon cards |

➕ = beyond source; captions cite e.g. ESC 2023 ACS guidelines / NICE CG95 / NICE NG185
(check latest versions).

## Pass criteria
- [ ] Welcome text matches `output-formats.md` §0
- [ ] Fact Sheet shown; T1–T4 and T7–T9 listed as separate facts
- [ ] Plan has ≥ 8 images (expected ~15) including the ➕ clinical block
- [ ] No image contains "T2–T9", "T1–T5", or "T7–T9" as the chest/arm referral levels
- [ ] Each image is single-concept (no multi-section poster, no "Key Takeaways" box)
- [ ] Whole heart is the main subject of only one image; patient clutching chest only once
- [ ] Batches of 4 with the `next` footer
- [ ] No doses inside images

## v1.1 failures this test catches
- Planned only 4 images; no treatment, investigations or drugs.
- All 7 images were multi-section posters repeating heart + spine + patient + oesophagus.
- Wrong levels in images: "T2–T9" (merged ranges), "T1–T5", "upper thoracic dermatomes
  (T7–T9)", and "MI involves the inferior wall" stated as if true of all MI.
- Custom welcome text → GPT was not using MedLens instructions.
