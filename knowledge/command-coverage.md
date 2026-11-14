# Command Coverage — which sheets each command makes

Every command makes **infographic sheets** (see `knowledge/visual-style-guide.md`).
**You decide how many sheets** the topic needs for `/medlens`, `/pathology`, `/tests` and
`/clinical`, and makes all of them in one reply — no fixed number. Only if the platform
stops: "Type continue for sheets N–M."
`/anatomy` and `/visualize` always make **exactly one image**. A command never makes sheets
that belong to another command, and never makes two versions of the same sheet. One sheet
covers one part of the topic with 4–8 sections; when a part has more than one sheet can hold
readably, split it. Never pad, never cut an important point.

Topic line shows the count: `🩺 Hypertension — Clinical: OPD · 4 sheets · Doctor`.
If the platform stops before all sheets are done, write `Type continue for sheets N–M.`

Layouts: **L1** atlas cross-section · **L2** info rows · **L3** step cards · **L4** photo
panel grid · **L5** drug cards · **L6** proforma dashboard · **L7** study notebook
(replaces the layout's look in `/student` and `/exam`).

---

## `/anatomy` — Pure gross anatomy plate

Topic = the organ/region in the screenshot (or typed after the command).
- **One ultra-detailed atlas plate** using Prompt A in `examples/master-prompts.md`:
  white background, heading "DETAILED ANATOMY OF THE HUMAN [ORGAN]", realistic 3D cutaway
  with external + internal anatomy, layers, vessels, nerves and relations, 20–30 labels with
  thin black leader lines (major → secondary → small).
- **Exactly one image.** Another view only when the user asks for it
  (`/anatomy posterior view`, `/anatomy blood supply`).
- Never pathway, pain-referral, symptom, dermatome or clinical posters — those belong to
  `/medlens`, `/visualize` and the other commands.
- **No disease, no treatment, no info cards.** Same look in every mode.
- If the screenshot is about a disease, draw the normal anatomy of the organ involved.
- End: `👉 Next: /visualize for the full overview, or /medlens for root cause & disease origin`.

## `/visualize` — Detailed overview poster

Topic = the organ, disease or medical topic in the screenshot (or typed).
- **Exactly one poster** using Prompt B in `examples/master-prompts.md`: deep
  midnight-navy theme, central 3D hero with 6–12 labels, 6–10 info cards.
- First identify the topic's category (anatomy, physiology, disease, examination/procedure,
  pharmacology, surgery) and choose only the relevant cards (table in master-prompts.md).
- No patient data, lab values or doses. Drug classes and first-line choices only.
- It is the overview; the other commands go deeper. Same look in every mode.
- End with the best deep-dive command for the topic.

## `/medlens` — Explain the whole topic of the screenshot

The main command. It must cover **everything the screenshot says**, in as many sheets as
that takes — no fixed number.

**Step 1 — concept list (silent).** Read the screenshot and list every concept it states,
in its order (e.g. for a cardiac-pain page: cause of the pain → afferent pathway → entry
into the cord at T1–T4 → referred skin areas → intercostobrachial nerve and medial arm →
neck and jaw → inferior-wall MI and T7–T9 epigastrium → oesophagitis mimic).

**Step 2 — one sheet per concept**, each a different part of the topic:

| Sheet | Layout | Contents |
|---|---|---|
| Detailed anatomy of the structures the source names | L1 | 15–30 labels; relations, blood/nerve supply when relevant. A second anatomy sheet for a second region the source names (e.g. heart **and** thoracic spinal nerves) |
| Normal function | L3 | How it works normally, 4–6 steps — only if needed to understand the topic |
| **Each concept from the list** | L2 / L3 / L1 as fits | The concept explained visually on the **exact organ or structure the source names** — never a generic organ picture |
| Root cause & starting point | L2 or L3 | Underlying cause(s); the exact site where the disease begins; how it spreads |
| First symptoms & key point | L2 | What the patient notices first and where; the source's key clinical/exam point |

**Exact references (mandatory)**
- Every organ, nerve, vessel, level and number named in the screenshot appears on a sheet,
  labelled with the **same words and numbers** (e.g. "upper four thoracic nerves (T1–T4)",
  "intercostobrachial nerve (T2)", "T7–T9").
- Each structure is drawn in its real anatomical position and relations.
- Never merge, round or "correct" the source's levels; separate statements stay separate.
- Nothing stated in the screenshot may be left out; nothing may be shown twice.
- Merge two small concepts into one sheet only if they share one picture.

Does **not** include: in-depth pathology, examination, investigations or treatment — those
are `/pathology`, `/tests` and `/clinical`.

End with a **recommended next command** (see "Choosing the next command").

## `/pathology` — The disease in depth

| Sheet | Layout | Contents |
|---|---|---|
| Causes & risk factors | L2 | Aetiology rows, modifiable vs non-modifiable |
| Pathogenesis | L3 | Molecular → cellular → tissue → organ steps |
| Gross & micro pathology | L2 + hero split image | Normal vs diseased organ; histology findings |
| Types / classification / staging | L2 or L3 | Each type with its key feature |
| Complications & prognosis | L2 | Local and systemic complications; prognostic factors |

## `/tests` — Clinical examination & diagnosis

| Sheet | Layout | Contents |
|---|---|---|
| History & examination format | L6 | Presenting complaint, HPI, past/family/personal history, general and systemic examination sections relevant to the topic |
| Examination techniques & signs | L4 | Inspection, palpation, percussion, auscultation, special signs — real photos of each being performed |
| Investigations: what they show | L2 | Each test → typical abnormal result → what it means (labs, imaging) |
| Interpretation method | L3 | e.g. ECG, X-ray, ABG step-by-step with normal vs abnormal examples |
| Scores, differentials & diagnosis path | L3 or L2 | Scores/criteria, look-alikes with distinguishing features, presentation → diagnosis |

## `/clinical` — Management (auto: OPD or Surgical)

Choose the pathway from the topic; user can force `/clinical opd` or `/clinical surgical`.
If both matter (e.g. ACS: medicines + PCI), make the main pathway and end with
"👉 Also available: /clinical surgical" (or opd).

### OPD pathway — conditions managed mainly with medicines

| Sheet | Layout | Contents |
|---|---|---|
| OPD plan | L3 | Assessment → diagnosis → targets → treatment steps (ladder) → follow-up |
| First-line medicines | **L5 drug cards** | Each drug: **name, Use, How it works, Why chosen, Side effects, Avoid in, Monitor** (+ Dose in `/doctor`) |
| Add-on / second-line medicines | **L5 drug cards** | When to add, which drug, why; combinations to avoid |
| Special groups | L5 or L2 | Pregnancy, elderly, kidney/liver disease, children — what changes and why |
| Lifestyle, follow-up & red flags | L2 | Non-drug measures, review schedule and targets, monitoring tests, when to refer or admit |
| Patient counselling | L2 (friendly) | How to take medicines, what to expect, warning signs |

**Drug card rules**
- Generic names; first-line choices per a named guideline (NICE, WHO, ESC, AHA/ACC, ADA,
  GINA, GOLD, local national guideline) — name it under the sheet.
- "Why chosen" is mandatory on every card.
- Doses: in the notes under the sheet by default. In `/doctor` mode a "Dose:" line may appear
  on the card with "Verify with formulary". Never doses in `/student`, `/exam` or `/patient`.

### Surgical pathway — conditions where surgery/procedure is key

| Sheet | Layout | Contents |
|---|---|---|
| Indications & decision | L3 | When to operate, when not to, conservative options |
| Pre-operative workflow | L2 or L3 | Assessment, investigations, consent, fasting, prophylaxis (antibiotics, VTE), marking, anaesthesia type |
| Operation step by step | Surgical L4 variant | Positioning, incision/ports, key steps, closure — realistic theatre images; open vs minimally invasive and why |
| Post-operative care | L4 or L2 | Analgesia, observations, drains, diet, mobilisation, wound care |
| Complications & discharge | L2 | Early/late complications and how they present; discharge criteria; follow-up |

---

## Choosing the next command (after `/medlens`)

| Topic type | Recommend |
|---|---|
| Disease mainly treated with medicines | `/pathology` → `/tests` → `/clinical` (OPD) |
| Disease mainly treated with surgery/procedure | `/pathology` → `/tests` → `/clinical` (Surgical) |
| Emergency condition | `/tests` first → `/clinical` |
| Pure anatomy / physiology concept | `/pathology` for the main disease it explains (name it) |

Format: `👉 Next: /pathology — then /tests and /clinical (OPD pathway)`.
After other commands, list the unused ones.

## No repeats (across all commands in a chat)
Each sheet covers a part not covered before, and the same hero visual is never reused.
A new screenshot resets this.
