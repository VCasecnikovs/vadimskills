---
name: finder
description: Open Finder at relevant location
user_invocable: true
---

# Finder Skill

Opens Finder at a relevant location based on context.

## Usage

- `/finder` - open Finder at current working directory
- `/finder <path>` - open Finder at specified path
- `/finder downloads` - open Downloads folder

## Shortcuts

Customize these to your own paths:

- `downloads` -> ~/Downloads
- `desktop` -> ~/Desktop

> Tip: Add your own shortcuts here - Obsidian vault, projects folder, etc.

## Instructions

1. Parse the argument (if any)
2. Resolve shortcuts to full paths
3. If no argument, use current working directory
4. Run `open <path>` to open Finder at that location
5. Confirm to user what was opened
