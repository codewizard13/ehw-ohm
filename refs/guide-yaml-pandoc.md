![Status: Draft](https://img.shields.io/badge/Status-DRAFT-orange?style=for-the-badge)


# 🧾 YAML + Pandoc Integration Guide  
*(How metadata and conversion work together in your Markdown workflow)*

***

## ⚙️ Overview

**Markdown is your core content format.**  
Pandoc serves as the **conversion engine** that turns these `.md` files into `.html`, `.pdf`, or `.docx` automatically using the YAML metadata embedded at the top of each document.

YAML is written in a simple, human-readable syntax and enclosed with delimiters (`---`). Pandoc reads this section before rendering to determine document metadata such as title, date, topic, author, or styling templates.

***

## 📦 YAML Front Matter Example

```yaml
---
title: "Why Covenant Matters"
topic: "Covenant"
type: "Teaching"
date: 2025-06-15
author: "Organic Harvest Ministries"
stylesheet: "../style.css"
template: "../templates/html/standard.html"
status: Published
---
```

### Pandoc Roles for Each Field

| Field | Used By Pandoc | Description |
|-------|----------------|-------------|
| `title` | Yes | Inserted into `<title>` and document headers |
| `author` | Yes | Auto-injected into metadata block |
| `date` | Yes | Auto-displayed in header/footer according to template |
| `topic` | No (custom) | Included as variable available to templates |
| `template` | Yes | Specifies which Pandoc template file to use |
| `stylesheet` | Yes | Adds linked CSS in HTML export |
| `status` | No (custom) | Available for internal metadata or publishing flags |

Pandoc stores any custom YAML keys as variables, accessible inside its templates using tokens like `$(topic)$` or `${topic}` depending on template syntax.

***

## 🔄 Conversion Workflow

When you run the export script or triggered command (from VSCode or PowerShell):

1. Pandoc reads each `.md` file inside `topics/`.
2. It parses YAML front matter and body content.
3. It references a base template (HTML, PDF, DOCX) specified in YAML or within the script.
4. It writes a corresponding `.html` file to `topics-htm/` preserving **identical folder hierarchy**.

The folder mirroring looks like this:

```text
topics/
│   covenant/
│   └── 20250615_SERMON__CovenantPeopleKingdomAssignment.md
│
topics-htm/
│   covenant/
│   └── 20250615_SERMON__CovenantPeopleKingdomAssignment.html
```

***

## 🧭 Recommended Folder Logic

| Purpose | Folder | Notes |
|----------|---------|-------|
| Primary Markdown source | `topics/` | Contains all ministry content; Markdown-first |
| Mirrored HTML export | `topics-htm/` | Created by Pandoc scripts automatically |
| Automation helpers | `tools/` | PowerShell, Node, Pandoc configs/scripts |
| Interim drafts | `drafts/` | Optional staging area before publishing |
| System support | `_sb/`, `_tmp/` | Ignored by automation; temporary or backup files |

**Main Workflow Summary:**
- You edit and save Markdown under `topics/`.
- A script or VSCode shortcut (e.g. `Ctrl+Shift+P → Run Pandoc Export`) executes conversion.
- The `topics-htm/` folder mirrors the structure and serves HTML outputs.

This design keeps the Markdown repository pure while maintaining fully synchronized output.

***

## 🧱 Automation Strategy

### Option 1 — PowerShell Script
You can use a batch-style PowerShell script (already compatible with Pandoc):

```powershell
Get-ChildItem -Path "topics" -Recurse -Filter *.md | ForEach-Object {
    $outputPath = $_.FullName -replace "topics", "topics-htm"
    pandoc $_.FullName -o ($outputPath -replace ".md$", ".html") --template=templates/html/standard.html --css=style.css
}
```

### Option 2 — VSCode Task or Extension
If using VSCode:
- Command: `Pandoc: Convert to HTML`
- Shortcut: `Ctrl+Shift+P` then select “convert folder”
- You can assign this to a workspace-level keybinding or task runner.

Recommended extension:  
**“Pandoc Document Converter”** or **“Markdown All in One”** — both support metadata-driven HTML exports.

***

## 🔍 Template Integration

Pandoc templates use token placeholders for YAML fields.  
Example snippet from `templates/html/standard.html`:

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>$title$ - Organic Harvest Ministries</title>
  <link rel="stylesheet" href="$stylesheet$">
</head>
<body>
  <header>
    <h1>$title$</h1>
    <p><em>$date$</em></p>
  </header>
  $body$
</body>
</html>
```

This makes YAML values dynamic — allowing you to control styles and metadata entirely from within each `.md` file.

***

## 🧾 Why Rename “docs/” to “ref/”

The name `docs/` often implies end-user documentation or public site pages.  
In your case, these files store technical reference material **for developers and contributors**, not ministry teachings. Therefore, **`ref/`** (short for **reference**) is semantically clearer and keeps the repo consistent with the Markdown-primary structure.

**New naming clarity:**
```text
ref/
├── naming.md
├── roadmap.md
├── pandoc-yaml.md
├── templates.md
├── exports.md
└── versioning.md
```

***

## 🪜 Next Steps

1. Rename `/docs/` → `/ref/`.  
2. Create `/topics-htm/` as your auto-export destination.  
3. Add Pandoc export script (`tools/export-html.ps1`) for full-folder mirroring.  
4. Add a `.vscode/tasks.json` triggering the same conversion command.  
5. Integrate this doc (`ref/pandoc-yaml.md`) for developers and team onboarding.  

***

Would you like me to draft the **actual PowerShell and VSCode task files** for this automation system next (so your Markdown-to-HTML mirror runs from one command or shortcut)?