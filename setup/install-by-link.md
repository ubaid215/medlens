# Install by Link (paste into any ChatGPT chat)

This loads MedLens **for one chat** by letting ChatGPT read the files from GitHub.
ChatGPT needs web access. For a permanent install, use the Custom GPT
(`custom-gpt-setup.md`) instead.

Replace `<your-username>` (and `main` if your default branch is different), then paste the
whole block into a new chat:

```
Install the MedLens skill for this chat. Read these files and follow them exactly for the
rest of this conversation. SKILL.md is the main instruction; safety-rules.md overrides
everything else.

https://raw.githubusercontent.com/<your-username>/medlens/main/SKILL.md
https://raw.githubusercontent.com/<your-username>/medlens/main/knowledge/coverage-checklist.md
https://raw.githubusercontent.com/<your-username>/medlens/main/knowledge/visual-style-guide.md
https://raw.githubusercontent.com/<your-username>/medlens/main/knowledge/safety-rules.md
https://raw.githubusercontent.com/<your-username>/medlens/main/knowledge/modes.md
https://raw.githubusercontent.com/<your-username>/medlens/main/workflows/full-run.md
https://raw.githubusercontent.com/<your-username>/medlens/main/workflows/commands.md
https://raw.githubusercontent.com/<your-username>/medlens/main/tools/image-generation.md
https://raw.githubusercontent.com/<your-username>/medlens/main/examples/image-prompt-templates.md
https://raw.githubusercontent.com/<your-username>/medlens/main/examples/output-formats.md

When you have read them, reply only: "✅ MedLens installed. Send a screenshot or type /help."
```

## Shorter version (if ChatGPT can open the repository page)
```
Install the MedLens skill from https://github.com/<your-username>/medlens — read SKILL.md and
every file it lists, follow them for this whole chat, then reply "✅ MedLens installed".
```

## Troubleshooting
- **"I can't access that URL"** → the repo must be **public**, and web search must be on.
  Otherwise use the Custom GPT, or attach the files directly to the chat.
- **It forgets the rules later in a long chat** → paste the install prompt again, or use the
  Custom GPT (its instructions are always loaded).
- **No images appear** → the chat or plan must have image generation available.
