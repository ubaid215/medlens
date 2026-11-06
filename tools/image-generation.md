# Tool — Built-in Image Generation

MedLens uses **only** the image generation built into the chat platform
(ChatGPT image generation). No external APIs, no API keys, no third-party links.

## Rules for calling the tool
1. **One image per call.** Never ask for a grid of unrelated images in one generation.
2. **Write the full prompt every time.** Do not rely on "same as before" — repeat the global
   style block so the look stays consistent.
3. **Quote exact label text**: `labels: "Left ventricle", "Aortic valve", "Mitral valve"`.
4. **Specify aspect ratio**: landscape 3:2 by default; portrait 2:3 for body maps/timelines.
5. **Say what to exclude**: "no extra text, no paragraphs, no watermark, no doses".
6. Generate images **sequentially**, writing each caption right after its image.

## Batching
- Default batch = 4 images per reply (`/next 6` allows up to 6).
- Long runs hit time and usage limits; batching keeps each reply reliable and lets the user
  steer between batches.
- Always end a batch with the progress line and the `next` instruction.

## When generation fails or is refused
- Do not silently skip. Say: "Image 7 could not be generated (reason if known)."
- Retry once with a simpler, more clinical prompt (fewer labels, less realism, no blood).
- If it still fails, write the caption text anyway and suggest `/only 7` later.
- If the user's plan limit is reached, tell them how many images are left and that
  `/only <numbers>` will resume later.

## Prompt skeleton
```
[IMAGE TYPE] of [SUBJECT] for medical education.
Show: [what must be visible, composition, view angle].
Labels (exact text): "…", "…", "…" (max 8).
Colour coding: normal green, disease red, treatment blue, warning orange, tests purple.
Style: [style block from visual-style-guide.md].
Aspect ratio: [3:2 | 2:3].
Exclude: extra text, paragraphs, doses, watermarks, identifiers, graphic gore.
Footer: small text "MedLens · Educational use".
```

## Platform notes
- **ChatGPT (Custom GPT)**: enable the *Image Generation* capability in Configure.
- **Other platforms with Agent Skills**: use that platform's built-in image tool if present.
  If the platform has **no** image tool, output the full prompt for each image in a code block
  under its plan number, so the user can generate it, and say so once at the start.
