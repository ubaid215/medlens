# Tool — Built-in Image Generation

MedLens uses **only** the image generation built into the chat platform
(ChatGPT image generation). No external APIs, no API keys, no third-party links.

## Rules for calling the tool
1. **One image per call.** Never a grid of unrelated images in one generation.
2. **Write the full prompt every time**, starting with the single-concept line and ending
   with the style and exclude blocks, so all images look consistent.
3. **Quote exact label text**: `labels: "Left ventricle", "Aortic valve", "Mitral valve"`.
4. **Aspect ratio**: landscape 3:2 by default; portrait 2:3 for body maps and flows.
5. **Say what to exclude**: "no extra text, no paragraphs, no poster layout, no legend,
   no logo, no watermark, no doses".
6. Generate the images **one after another**, writing each image's notes right after it.

## How many per reply
The model decides the number from the topic (see `knowledge/command-coverage.md`).
If the platform stops before all are done, the user types `continue` and you carry on
from the next image.

## When generation fails or is refused
- Never skip silently. Say which image failed (reason if known).
- Retry once with a simpler, more clinical prompt (fewer labels, less realism, no blood).
- Still failing: write its notes anyway and suggest `/redo N` later.
- Plan limit reached: say which images are missing; `/redo N` retries each one.

## Prompt skeleton
```
Single-concept medical illustration, NOT an infographic poster, no paragraphs of text.
[IMAGE TYPE] of [SUBJECT] for medical education.
Show: [what must be visible, composition, view angle].
Labels (exact text): "…", "…", "…" (max 8).
Colour coding: normal green, disease red, treatment blue, warning orange, tests purple.
Style: [style block from visual-style-guide.md].
Aspect ratio: [3:2 | 2:3].
Exclude: extra text, paragraphs, poster layout, legend, logo, doses, watermarks, identifiers, gore.
Footer: small text "MedLens · Educational use".
```

## Other platforms
No built-in image tool (e.g. Claude) → **Claude mode**, see `tools/claude-rendering.md`.
