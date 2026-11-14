# Regression Test — "Cardiac Pain" clinical notes page

Use after any change. Source: textbook "Clinical Notes — Cardiac Pain" box.

## Facts the sheets must respect
1. Afferents ascend via **cardiac branches of the sympathetic trunk**.
2. Enter the cord via **posterior roots of the upper four thoracic nerves (T1–T4)**.
3. Referred to skin of the upper four intercostal nerves + **intercostobrachial nerve (T2)**
   → **medial upper arm**; sometimes **neck and jaw**.
4. Pain ranges from severe crushing to mild discomfort.
5. **Inferior-wall/diaphragmatic MI → T7–T9 → epigastrium.** Separate from fact 2.
6. Acute oesophagitis can mimic MI.

## Expected sheets (count decided by the model)

| Command | Must include |
|---|---|
| `/anatomy` | One white atlas plate "DETAILED ANATOMY OF THE HUMAN HEART": chambers, valves, coronary arteries, great vessels, cardiac plexus; 20–30 labels; no ischaemia or pain content |
| `/visualize` | One navy poster "CARDIAC PAIN": hero = heart with cardiac nerves to T1–T4; cards: definition, cause (ischaemia), pain pathway, referred areas, inferior-wall MI → T7–T9 epigastrium, differentials (oesophagitis); no doses |
| `/medlens` | L1 atlas sheet: heart, cardiac nerves, sympathetic trunk, T1–T4 roots; L3 pathway steps (ischaemia → metabolites → nerve endings → T1–T4 → dorsal horn convergence); L2 referred areas (chest, medial arm T2, neck, jaw) and inferior-wall MI → T7–T9 epigastrium. Next: `/pathology` (acute coronary syndrome) or `/tests` first |
| `/pathology` | Risk factors; plaque → rupture → thrombus → ischaemia → infarction; healthy vs blocked artery + infarct histology; types (STEMI/NSTEMI/unstable angina); complications |
| `/tests` | L6 chest-pain history & examination proforma; L4 examination photos; L3 ECG interpretation steps with ST-elevation example; L2 troponin and other tests; differentials (oesophagitis, PE, dissection) |
| `/clinical` | Auto both: L3 plan; L5 drug cards (antiplatelets, anticoagulant, nitrate, beta-blocker, statin — each with Why); PCI step sheet; secondary prevention; "👉 Also available: …" |

## Pass criteria
- [ ] `/help` shows the exact v4.1 welcome text
- [ ] **Every command generates sheets** — no text article, no web thumbnails or links
- [ ] Topic line shows command, sheet count and mode
- [ ] Sheets are portrait, detailed and readable (title band, 4–8 sections, tip box)
- [ ] Read-back clean: no misspellings, invented words, duplicate sections or impossible values
- [ ] No sheet says "T2–T9", "T1–T5", or puts chest/arm pain at T7–T9
- [ ] No logos, handles, websites or watermarks
- [ ] Every drug card has a "Why:" line; guideline named under the sheet
- [ ] Doses only in `/doctor` (with "Verify with formulary"); none in student/exam/patient
- [ ] `/student` and `/exam` use the notebook look; `/exam` adds MCQ/viva with answers
- [ ] No part or hero visual repeated across commands

## Earlier failures this test catches
- v1.1: posters repeating heart + spine + patient; wrong levels (T2–T9, T1–T5).
- v1.2: treatment posters with unverified doses and a third-party logo.
- v3.0 (link install, web search on): text article with web thumbnails, **no generated images**.
