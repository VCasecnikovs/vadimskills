---
name: typora
description: Open markdown files in Typora editor for comfortable reading
user_invocable: true
---

# Open in Typora

Open a markdown file in Typora for viewing or editing. Claude Code's console only shows diffs and raw text - Typora renders full markdown with formatting, images, and clickable links.

## Behavior

1. Identify the file to open from conversation context:
   - User specifies a path directly
   - User references a recently created/edited file
   - User says "open it" / "show me" after Claude generated a .md file
2. Open with:
   ```bash
   open -a Typora "FILE_PATH"
   ```
3. Confirm briefly what was opened

## Rules

- Works with `.md` files primarily
- If file path is ambiguous, search with Glob first
- If Typora is not running, it will launch automatically
- If file doesn't exist, tell the user instead of creating it

## Why This Exists

Claude Code generates great markdown - research docs, plans, reports. But in the console you only see edit diffs, no formatting, no images. Typora gives you the full rendered view and even lets you watch Claude write in real time.
