# Claude Code macOS Bridge Skills

Skills that fix Claude Code's terminal limitations by bridging to native macOS apps.

## The Problem

Claude Code is incredibly powerful, but its terminal holds it back:
- You can't read formatted markdown in the console
- Copying text grabs line number padding
- Long reports are impossible to study while typing
- Saved files vanish into deep directory trees

## The Skills

### /typora
Opens `.md` files in [Typora](https://typora.io/) for full rendered viewing. Claude Code's main output format is markdown, but the console only shows diffs - no formatting, no images, no clickable links.

### /copy
Puts clean text in your clipboard via `pbcopy`. When you copy from Claude Code's console, every line grabs padding from line numbers. This skill extracts just the content.

### /html-view
Renders output as a styled HTML page and opens in the browser. When Claude Code gives you a 20-item report, you can't scroll up and type at the same time - any keystroke snaps the view back to the bottom. Read in Safari, type in the terminal.

### /finder
Opens Finder at the location where Claude Code saved a file. Paths flash by in the output and disappear. This gets you right there.

### /web
Proactively opens relevant web pages after actions that have a web counterpart. Push to GitHub? It opens the repo. Create a PR? It opens the PR. Deploy? It opens the site. Also works manually with `/web`.

## Installation

Copy any skill folder into your Claude Code skills directory:

```bash
cp -r typora/ ~/.claude/skills/typora/
cp -r copy/ ~/.claude/skills/copy/
cp -r html-view/ ~/.claude/skills/html-view/
cp -r finder/ ~/.claude/skills/finder/
cp -r web/ ~/.claude/skills/web/
```

Each skill is a single `SKILL.md` file - plain text instructions, no code.

## Usage

In Claude Code, just type:
- `/typora` - open current file in Typora
- `/copy` - copy last relevant output to clipboard
- `/html-view` - render output as HTML page
- `/finder` - open Finder at relevant location
- `/web` - open relevant web page (also triggers proactively)

## Requirements

- macOS (uses `open`, `pbcopy`)
- [Typora](https://typora.io/) for the `/typora` skill
- Claude Code with skills support
