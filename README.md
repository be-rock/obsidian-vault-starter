---
name: Obsidian Vault Starter
---

# README

This is a working Obsidian vault that favors lightweight structure over heavy tooling. The goal is simple: capture quickly, organize with tags and Bases, and keep everything in plain Markdown so it plays nicely with AI.

## Why this setup works

- **Markdown-first** keeps notes portable, readable, and easy to automate.
- **Tags + Bases** give you dashboards without losing freeform writing.
- **Templates + hotkeys** reduce friction so capture stays consistent.
- **Agent-friendly** structure lets Cursor/Claude automate setup and upkeep.

## How to use this repo

### Use as a new vault

1. Clone the repo.
2. Open the repo root in Obsidian as a vault.
3. Enable community plugins when prompted.

### Merge into an existing vault

Copy the repo contents into your existing vault root and overwrite when prompted. The structure is designed to drop in cleanly.

## Vault layout (root-level)

```
_bases/
_daily/
_templates/
Meetings/
Notes/
People/
Projects/
Tasks/
Topics/
.obsidian/
.claude/
```

## Templates (and why)

- `daily.md` is your periodic note. Use it to log quick context, but keep most content in meetings or unique notes. The embedded Bases make it a lightweight dashboard for creating or jumping to the notes you need.
- `unique-note.md` gives fast, timestamped capture for ad-hoc notes.
- `project.md` and `task.md` standardize fields like `status`, `priority`, `due`.
- `meeting.md`, `person.md`, `company.md` keep CRM-style notes consistent.

**Hotkeys**

- `Cmd + D` creates or opens the daily note.
- `Cmd + Shift + N` creates a timestamped unique note via ZK Prefixer.

## Bases (the dashboards)

- `Projects.base` is the master list for projects + tasks, plus “Due This Week.”
- `Meetings.base` keeps meeting notes visible by recency.
- `People.base` tracks people and follow-ups.

These Bases are embedded in `daily.md` so your daily note becomes your dashboard.

## Tags (the “type system”)

This vault standardizes on tags:

- `project` for project notes
- `task` for tasks
- `meeting` for meetings
- `person` for people
- `note` for unique notes captured
- `topic` for longer lived domain topics

This keeps filtering simple and consistent.

## Commands and workflows

### Daily workflow

1. Hit `Cmd + D` to open today’s daily note.
2. Review the embedded Bases (tasks, meetings, people follow-ups).
3. Capture quick context, then create a meeting or unique note for the real content.

### Task workflow: turn todos into tasks

Use the custom command `/sync-todos`:

1. Search for unchecked todos (`- [ ]`) across the vault.
2. Convert each todo into a task note in `Tasks/`.
3. Backlink the original note so context stays connected.

This keeps scattered todos from getting lost.

## Plugins

Community plugins are focused on speed and consistency:

- Calendar + Periodic Notes for daily capture
- Templater for flexible templates
- Natural Language Dates for quick date entry
- Notebook Navigator + Icon Folder for navigation
- Excalidraw for sketches
- Filename Heading Sync to keep titles consistent

Core plugin toggles are stored in `.obsidian/core-plugins.json`.

## Skills and automation

Skills are consolidated under `.cursor/skills/` so Cursor/Claude can reuse them:

- Obsidian Markdown
- Obsidian Bases
- JSON Canvas
- QMD vault search

Obsidian skills are sourced from:
https://github.com/kepano/obsidian-skills/tree/main/skills

QMD docs:
https://github.com/tobi/qmd