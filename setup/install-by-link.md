# Quick Install in One Chat (no Custom GPT)

For a permanent install use the **Custom GPT** (`custom-gpt-setup.md`) — it is the most
reliable way. Use this page only to try MedLens in a normal ChatGPT chat.

## Recommended: paste the instructions (no web needed)

1. Open a **new** ChatGPT chat with image generation available. Turn **web search off**.
2. Open [`instructions/gpt-instructions.md`](../instructions/gpt-instructions.md), copy
   **all** of it.
3. Paste it as your first message, with this line on top:

```
Follow these instructions as your rules for this whole chat. Do not summarise them.
Reply only with the MedLens welcome text.
```

4. ChatGPT replies with "🩺 MedLens v4 ready." Now upload your screenshot and type a command.

## Why not just paste the GitHub link?

Reading a link makes ChatGPT use **web search**. In that mode it tends to summarise the
repository and answer with a **text article and web thumbnails instead of generating
sheets**, and it takes facts from the web instead of your screenshot. Pasting the
instructions avoids all of that.

If you still want the link, use only the single instructions file:
```
Read https://raw.githubusercontent.com/ubaid215/medlens/main/instructions/gpt-instructions.md
and follow it as your rules for this whole chat. Do not summarise it. From now on do NOT use
web search or web images — always generate the sheets with the image tool.
Reply only with the MedLens welcome text.
```

## Troubleshooting
- **Text article or web pictures instead of sheets** → web search was on. Start a new chat,
  turn web search off, and use the paste method.
- **It forgets the rules in a long chat** → paste the instructions again, or use the Custom GPT.
- **No images at all** → your plan or chat has no image generation available.
