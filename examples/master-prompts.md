# Master Prompts — `/anatomy` and `/visualize`

Use these prompts as written. Fill every `[bracket]` from the screenshot's topic.
The **LABELS / CARD TEXT** blocks are mandatory: write the exact words yourself, in quotes,
so the image tool never invents or misspells text. After generating, do the read-back check
(`knowledge/visual-style-guide.md` §6).

---

## Prompt A — `/anatomy` (pure gross anatomy plate)

```
Create an ULTRA-HIGH-RESOLUTION, scientifically accurate, extremely detailed medical
textbook anatomical illustration of the HUMAN [ORGAN NAME].

REFERENCE STYLE:
Follow the visual style of premium medical anatomy textbooks, professional anatomical
atlases, and advanced medical educational wall charts. The illustration must look like a
professionally hand-rendered anatomical plate, combining realistic 3D anatomical rendering
with precise medical textbook illustration. Original artwork — do not copy any named atlas.

1. ANATOMICAL PRESENTATION
Show the complete human [ORGAN NAME] in a detailed anatomical cutaway view
([VIEW: e.g. anterior view, left side sectioned]). Include its external anatomy, internal
anatomy, surrounding structures, cross-sectional layers, and important anatomical
relationships. Reveal internal structures through carefully designed sectional views
without hiding the recognizable overall shape of the organ.

2. EXTREME ANATOMICAL DETAIL
Accurately illustrate all relevant structures, including: major and minor anatomical
components; muscles and muscle layers; arteries and veins; nerves and nerve branches; bones
and cartilage where applicable; ligaments and connective tissues; membranes and epithelial
layers; internal cavities and chambers; ducts, channels and passageways; glands and
associated structures; microscopic or cellular details where relevant (as a small inset).
Include smaller anatomical structures often omitted from simplified illustrations.

3. MULTIPLE ANATOMICAL VIEWS
Integrate where anatomically relevant: external view, internal cutaway, cross-section, deep
structures, important surrounding relationships. Maintain correct anatomical orientation
(never mirrored), proportions and spatial relationships.

4. SCIENTIFIC LABELING
Add clear, professional anatomical labels. Use thin, precise black leader lines connecting
each label to the exact structure. Arrange labels around the organ without covering
anatomy. Organize hierarchically: major structures, secondary structures, smaller
components.
LABELS — use ONLY these, spelled exactly, each once:
Major: "[label]", "[label]", "[label]", …
Secondary: "[label]", "[label]", …
Small components: "[label]", "[label]", …
(20–30 labels in total, 1–4 words each.)
No duplicated labels, no incorrect pointers, no misspellings, no invented structures,
no other text.

5. VISUAL DESIGN
Clean white or very light neutral background. Large professional heading at the top:
"DETAILED ANATOMY OF THE HUMAN [ORGAN NAME]". Anatomically realistic natural tissue colors
with distinct differentiation between tissues (arteries red, veins blue, nerves yellow,
bone ivory, muscle red-brown, lymphatics green). Highly detailed textures and realistic
depth, fine anatomical boundaries, professional textbook typography, balanced educational
poster composition with labels positioned around the central illustration.

6. SCIENTIFIC ACCURACY
Anatomical correctness is the highest priority. Do not invent structures, distort
proportions, confuse adjacent structures, or add decorative elements that obscure anatomy.
Every visible structure must correspond to real human anatomy.

7. OUTPUT QUALITY
Professional medical atlas quality, ultra-detailed rendering, sharp edges and fine tissue
details. High-resolution educational poster, portrait 2:3, largest available size.
No logos, watermarks, social handles, websites or brand names.
Small footer text: "MedLens · Educational use".
```

**Rules for `/anatomy`**
- Pure gross anatomy only — no disease, no treatment, no clinical boxes.
- **Exactly one image.** Another view only when the user asks
  (`/anatomy posterior view`, `/anatomy blood supply`).
- Never pathway, pain-referral, dermatome, symptom or clinical posters in `/anatomy`.
- Labels: copy names exactly from the screenshot first, then add standard anatomical names.
  If more than 30 structures matter, split into a second plate instead of smaller text.
- Notes under the plate: 2–4 bullets (orientation, what the section shows, one clinical
  relevance line).

---

## Prompt B — `/visualize` (comprehensive topic poster)

```
Create an ULTRA-HIGH-RESOLUTION, scientifically accurate, comprehensive medical educational
infographic poster about: "[ORGAN / DISEASE / MEDICAL TOPIC]".

REFERENCE DESIGN:
Follow the visual language of premium medical educational posters, advanced clinical
atlases, professional medical infographics and modern clinical reference charts — a
professionally designed medical textbook poster combining a realistic 3D anatomical
illustration, detailed clinical diagrams and organized information panels.

CENTRAL HERO ILLUSTRATION:
A large, visually dominant, anatomically accurate 3D medical illustration in the centre:
[HERO: e.g. cutaway of the inflamed appendix on the caecum showing lumen obstruction].
Realistic proportions, correct relationships, natural tissue colors, detailed textures,
realistic lighting and professional 3D depth. It is the main visual focus.
Leader-line labels on the hero — ONLY these, spelled exactly: "[label]", "[label]", …
(6–12 labels).

INFORMATION PANELS:
Compact, clearly separated information cards on a modular grid — left and right sidebars
and a lower section. Use ONLY these cards and this text, spelled exactly:
Card "[HEADING 1]": "[line]" · "[line]" · "[line]"
Card "[HEADING 2]": "[line]" · "[line]" · "[line]"
…
(6–10 cards; heading ≤ 3 words; ≤ 3 lines per card; ≤ 7 words per line.)

SUPPORTING DIAGRAMS:
[2–4 small supporting illustrations placed inside the relevant cards, e.g. cross-section,
microscopic view, examination diagram, imaging example, flow arrows.] Use arrows for
direction, progression and pathways. Every visual must help explain the topic.

LAYOUT:
Header: large uppercase title "[TITLE]" and subtitle "[subtitle]".
Centre: the 3D hero. Sidebars: supporting cards. Lower section: diagnosis, investigations,
management, complications. Consistent spacing, alignment, margins and hierarchy.

COLOR AND DESIGN SYSTEM:
Background deep midnight navy and dark medical blue. Dark navy cards with subtle borders
and a subtle glass effect. Accents: electric cyan, teal, turquoise, soft blue. Anatomy in
realistic biological colors. White headings, light grey supporting text, restrained accent
highlights. Soft illumination, controlled gradients, refined shadows. Excellent contrast
and readability; no excessive neon, no unnecessary decoration.

ACCURACY AND TEXT:
Medical correctness is the highest priority. Correct terminology and anatomical names,
accurate proportions, labels pointing to the correct structures. No duplicated or invented
structures, no fabricated clinical findings, no patient demographics, no laboratory values,
no drug doses, no placeholder or meaningless text, no misspellings. Use only the quoted
text above.

OUTPUT:
Premium medical educational poster, portrait 2:3, largest available size, ultra-detailed,
sharp, professional; dense but organized. No logos, watermarks, social handles, websites or
brand names. Small footer text: "MedLens · Educational use".
```

**Choosing the cards for `/visualize`** — first identify the topic's category, then pick
only relevant cards (never force irrelevant ones):

| Topic category | Typical cards |
|---|---|
| Organ / anatomy | Overview · Location · External structures · Internal structures · Relations · Blood supply · Nerve supply · Function · Clinical correlation |
| Physiology | Overview · Mechanism steps · Regulation · Functional pathway · Clinical correlation |
| Disease | Definition · Causes & risk factors · Pathophysiology · Clinical features · Examination · Investigations · Diagnosis · Management · Complications |
| Clinical examination / procedure | Purpose · Preparation · Steps · Normal findings · Abnormal findings · Special tests · Pitfalls |
| Pharmacology | Drug class · Mechanism · Uses · Side effects · Contraindications · Monitoring (no doses) |
| Surgery | Indications · Pre-op · Key steps · Post-op care · Complications |

**Rules for `/visualize`**
- **Exactly one poster** that gives the whole picture of the topic.
- It is the overview; the deep-dive commands (`/medlens`, `/pathology`, `/tests`,
  `/clinical`) go further. Recommend the best one as the next step.
- Management card names drug **classes and first-line choices only** — never doses.
- Notes under the poster: 2–4 bullets + guideline name if management is shown.
