# Command Coverage — what each command must cover

**You decide how many images.** Make as many as the topic needs to be fully understood —
one idea per image, no filler, no repeats. A small concept may need 3; a major disease may
need 10 or more. Never pad, never cut an important point to save images.

State the count on the topic line: `🩺 Appendicitis — Anatomy & Origin · 6 images`.
If the platform stops before all images are done, the user types `continue`.

---

## `/medlens` — Anatomy, root cause, and where the disease starts

Always the first command for a new screenshot. Cover, as needed:
- **Normal anatomy** of every structure involved (3D, labelled), including relations,
  blood supply, nerve supply, lymphatics when relevant.
- **Normal function** the disease disrupts.
- **Root cause** — the underlying cause (e.g. obstruction, ischaemia, infection,
  autoimmunity, mutation, trauma).
- **Starting point** — the exact site where the disease begins, shown in its anatomical
  context (e.g. appendix lumen obstruction by faecolith; coronary plaque in the LAD).
- **How it spreads / first changes** from that starting point.
- **What the patient first notices** — early symptoms and where they are felt.
- The screenshot's **key point** (special case, classic exam fact).

End with a **recommended next command** (see "Choosing the next command").

## `/pathology` — The disease in depth

Cover, as needed:
- Aetiology and risk factors
- Pathogenesis step by step (molecular → cellular → tissue → organ)
- Gross pathology (healthy vs diseased)
- Microscopic / histopathology findings
- Types, classification or staging
- Natural history if untreated
- Complications (local and systemic)
- Prognostic factors

## `/tests` — Clinical examination and diagnosis

Cover, as needed:
- **History**: key symptoms and questions to ask
- **Clinical examination**: inspection, palpation, percussion, auscultation; special signs
  and manoeuvres (e.g. McBurney's point, Rovsing's sign, Murphy's sign) — shown being
  performed in a realistic clinic/bedside scene
- **Bedside tests** (e.g. ECG, urine dip, glucose)
- **Laboratory tests** with typical abnormal results
- **Imaging** with typical findings (X-ray, ultrasound, CT, MRI)
- **Scores / criteria** (e.g. Alvarado, CURB-65, Wells)
- **Differential diagnosis** — how to tell look-alikes apart
- **Diagnosis pathway** — presentation → tests → diagnosis

## `/clinical` — Management (auto: OPD or Surgical)

The model decides the pathway from the topic (see below). The user can force one:
`/clinical opd` or `/clinical surgical`.

### OPD / medical pathway
For conditions managed mainly with medicines and follow-up (e.g. hypertension, diabetes,
asthma, GERD, stable angina, hypothyroidism).
- OPD consultation flow: assessment → diagnosis → plan
- **First-line medicine**: which drug, how it works (mechanism image), **why it is chosen**
- Second-line / add-on options and when to step up (treatment ladder)
- Side effects to watch, who should not take it, monitoring tests
- Lifestyle and non-drug management
- Follow-up schedule and targets
- Red flags → when to refer or admit
- Patient counselling points

### Surgical pathway
For conditions where surgery or a procedure is the key treatment (e.g. appendicitis,
hernia, cholecystitis, fractures, CABG/PCI, tumours).
- **Indications** for surgery (and when not to operate)
- **Pre-operative workflow**: assessment, investigations, consent, fasting, prophylaxis
  (e.g. antibiotics, VTE), marking
- **Anaesthesia** type
- **Operative steps** in order (positioning, incision/ports, key steps, closure) —
  realistic OR scenes, non-graphic
- Open vs minimally invasive options and **why one is chosen**
- **Post-operative care**: analgesia, monitoring, drains, mobilisation, diet
- **Post-op complications** and how they present
- Discharge criteria and follow-up

### Both
If a condition has an important medical **and** surgical/procedural part (e.g. acute
coronary syndrome: medicines + PCI), cover the main pathway and end with
"Also available: /clinical surgical" (or opd).

---

## Choosing the next command (after `/medlens`)

Always end `/medlens` with one recommendation line, chosen from the topic:

| Topic type | Recommend |
|---|---|
| Disease mainly treated with medicines | `/pathology` → `/tests` → `/clinical` (OPD) |
| Disease mainly treated with surgery/procedure | `/pathology` → `/tests` → `/clinical` (Surgical) |
| Emergency condition | `/tests` first (diagnosis is urgent) → `/clinical` |
| Pure anatomy / physiology concept (no disease named) | `/pathology` for the main disease it explains (name it) |

Format: `👉 Next: /pathology — then /tests and /clinical (Surgical pathway)`.
After the other commands, show the remaining unused ones.

---

## No repeats (across all commands in a chat)

Keep a list of what was already drawn. Each new image must show something new; the same
main picture (whole organ, spine, patient holding abdomen/chest…) is never the main
subject twice. A new screenshot resets the list.
