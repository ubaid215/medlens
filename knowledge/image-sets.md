# Image Sets — exactly 4 images per command

Every command makes **exactly 4 images**, each teaching one thing. Adapt each slot to the
topic in the screenshot; keep the slot's purpose.

## `/medlens` — Explain the topic (first command)

| # | Slot | Shows | Typical style |
|---|---|---|---|
| 1 | **Structure** | The body part involved, healthy, labelled | 3D anatomical render |
| 2 | **How it works** | The core process the source explains (pathway, mechanism, flow) | 3D + arrows, or 3–4 step panels |
| 3 | **What the patient feels / shows** | Symptoms and signs where they appear on the body | Body map |
| 4 | **Key point** | The single most important clinical or exam point from the source (a special case, a look-alike condition, a classic sign) | Focused 3D or comparison |

## `/pathology` — What goes wrong

| # | Slot | Shows | Typical style |
|---|---|---|---|
| 1 | **Causes & risk factors** | What triggers the disease | Organ in centre + risk icons |
| 2 | **Disease process** | Step-by-step change from healthy to diseased | 3–4 numbered panels |
| 3 | **Healthy vs diseased** | Same structure side by side + microscopic inset | 3D split view |
| 4 | **Complications** | What happens if untreated | 3D / body map with callouts |

## `/tests` — How it is diagnosed

| # | Slot | Shows | Typical style |
|---|---|---|---|
| 1 | **Bedside findings** | Key examination signs | Realistic clinic scene or body map |
| 2 | **Key test 1** | e.g. ECG, X-ray, ultrasound — the typical abnormal finding | Clean panel |
| 3 | **Key test 2** | e.g. blood test, biopsy, scan — abnormal values/finding | Clean panel |
| 4 | **Diagnosis path** | Short flow from presentation to diagnosis (max 6 boxes) | Flowchart |

## `/treatment` — What we do, which medicine, and why

| # | Slot | Shows | Typical style |
|---|---|---|---|
| 1 | **Treatment plan** | First step → next step → when to escalate (max 5 boxes, no doses) | Simple ladder / flow |
| 2 | **Main medicine** | The first-line drug class: where it acts and what it does; label "Why: …" | 3D mechanism |
| 3 | **Procedure or surgery** | The key procedure in a realistic hospital setting (if none exists: the second drug class) | Realistic scene |
| 4 | **Recovery & prevention** | Lifestyle, follow-up, warning signs to return | Simple icon cards |

The **text under the images** gives the full "which and why":
- Medicines: name + class, **why chosen**, main side effects, who should not take it.
- Procedure/surgery: what it is, **when it is chosen over medicines**.
- Guideline named (NICE, ESC, AHA/ACC, WHO, ADA…). Doses only in text, only for doctors,
  always with "verify with local formulary/BNF".

## No repeats (across all commands in a chat)

Keep a list of what was already drawn. Each new image must show something new; the same
main picture (whole heart, spine, patient holding chest…) is never the main subject twice.
