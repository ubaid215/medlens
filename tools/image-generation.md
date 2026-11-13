# Tool — Built-in Image Generation

MedLens uses **only** the image generation built into the chat platform (ChatGPT image
generation). No external APIs, no API keys, **no web search, web images or links**.

## Images first
- Every command must call the image tool. A reply without generated sheets is a failure.
- Topic line, then sheet 1 straight away. Do not write an explanation first.

## Rules for calling the tool
1. **One sheet per call.** Each call produces one complete infographic sheet.
2. **Portrait 2:3 at the largest size available** (e.g. 1024×1536 or higher).
3. **Write the full prompt every time**: opening line + layout template + every word of
   text in quotes + text rules/exclude line. Never "same as before".
4. **Tell the tool to use only the quoted text**, spelled exactly, in a large clear font.
5. **Exclude**: logos, watermarks, social handles, websites, brand names, paragraphs, tiny
   print, gore.
6. Keep the same theme and section colours across all sheets in one reply.

## Read-back after each sheet
Read every visible word and number. Misspelling, invented text, wrong number, duplicated
section, impossible value or a logo → remake once with less text. Still wrong → say exactly
what is wrong in the sheet's notes.

## How many per reply
The model decides from the topic (`knowledge/command-coverage.md`). If the platform stops
before all sheets are done: "Type continue for sheets N–M." On `continue`, carry on.

## When generation fails or is refused
- Never skip silently; say which sheet failed (reason if known).
- Retry once with a simpler prompt (fewer sections, less realism, no blood).
- Still failing: give its notes and suggest `/redo N` later.

## Other platforms
No built-in image tool (e.g. Claude) → **Claude mode**, see `tools/claude-rendering.md`.
