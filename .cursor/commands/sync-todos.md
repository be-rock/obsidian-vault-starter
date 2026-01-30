Sync TODO bullets into task notes

Goal: Find all unchecked todo bullets, understand their context (headers + parent bullets),
and create task notes that will show up in `/_bases/Projects.base`.

1) Find all todo bullets with surrounding context

Run this from the vault root:

```sh
rg -n --multiline '^[\t ]*[-*+] \[ \]' -C 6 "<vault-root>"
```

Notes:
- `-C 6` shows surrounding lines so you can capture parent sections/bullets
  (e.g., "Mobsec").
- Add `--glob "*.md"` to limit to Markdown only.

2) Extract full context for each todo

For each match, capture:
- The todo text itself
- The nearest parent bullet (if nested)
- The nearest relevant header (if any)
- The source note path

Use that context to form a clearer task title/description, e.g.:
"Mobsec: Install on phone" instead of "Install on phone".

3) Create a task note per todo

Place in `Tasks/` so `/_bases/Projects.base` picks it up.
Use this frontmatter shape:

```
---
status: "To Do"
priority:
due:
tags:
  - task
description: <full context todo text>
Topics: "[[<source note>]]"
---
```

4) Backlink the source todo

Insert a backlink to the new task note at the same location as the
original todo bullet (inline or on the next line). Example:

- [ ] Install on phone -> [[Tasks/Task - Install On Phone]]
