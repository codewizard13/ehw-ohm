> ⚠️ **DRAFT VERSION — WORK IN PROGRESS**  
> _This document is under active development and may change substantially._

![Status: Draft](https://img.shields.io/badge/Status-DRAFT-orange?style=for-the-badge)


# ✝️ Organic Harvest Ministries — Teaching & Handout Repository

> **Markdown-first, Spirit-led document system** for sermons, outlines, decrees, and handouts.
> Designed for clarity, reusability, and Kingdom excellence.

---

## 📖 Purpose
A **structured, version-controlled library** for all teaching materials. Each document is maintained as Markdown (`.md`), enabling rich revision history, easy export, and ministry-wide clarity.

**Key outcomes:**
- 🔹 Fast drafting and revision  
- 🔹 Consistent, reusable templates  
- 🔹 Automated export to HTML, PDF, DOCX  
- 🔹 [Template formatting details ›](docs/templates.md)

***

## 🗂️ Folder Structure Overview

### Simplified Tree

```text
D:.
│   README.md
│   style.css
│   .gitignore
│
├───docs/
├───templates/
├───drafts/
├───output/
├───topics/
├───tools/
└───_sb/
```

### Detailed Breakdown

```text
├───docs/
│   ├── exports.md
│   ├── naming.md
│   ├── roadmap.md
│   ├── styleguide.md
│   ├── templates.md
│   └── versioning.md
│
├───templates/
│   ├───html/
│   ├───markdown/
│   └───includes/
│
├───drafts/
│   └───archive/
│
├───output/
│   ├───html/
│   ├───pdf/
│   ├───docx/
│   └───logs/
│
├───topics/
│   ├───biblical-covenant/
│   ├───biblical-time/
│   ├───decrees/
│   ├───foolish-cross/
│   ├───jesus-genealogy-prophecy/
│   ├───matthew-kingdom-parables/
│   ├───music/
│   └───unsorted-lessons/
│
├───tools/
│   ├── pandoc/
│   ├── powershell/
│   └── nodejs/
│
└───_sb/
    └───_tmp/
```

- Folders prefixed with `_` (e.g., `_sb`, `_tmp`) are **ignored by automation or exports**.
- All public/exported content resides in non-prefixed folders.

***

## 🧭 Workflow Summary

1. **Draft in Markdown** with structured YAML front matter.  
2. **Apply templates** using include tokens.  
3. **Export automatically** via PowerShell or Node scripts using Pandoc + wkhtmltopdf.  
4. **Style and publish** consistently with shared CSS.

Quickstart examples (from both versions):
- Draft (v2 example): `notepad .\topics\biblical-covenant\20250615_TEACHING__WhyCovenantMatters.md`  
- Draft (v1 path example, kept for reference): `notepad .\_topics\Covenant\teachings\20250615_TEACHING__WhyCovenantMatters.md`  
- Export: `.\Export-Markdown-v2.ps1`  
- View: open HTML or PDF in `/output/`

***

## 🧩 Templates & Include Tokens

Use preapproved snippets and ministry-standard layout components:

- **Markdown tokens:**  
  `{{include templates/markdown/handout_header.md}}`
- **HTML templates:**  
  Structured for Pandoc conversion  
- [Template reference ›](docs/templates.md)

(Alternate token paths seen in earlier drafts: `{{include _templates/markdown/handout_header.md}}` — canonical path follows templates/ above.)

***

## 🧱 Naming, Metadata & Versioning

Use consistent format:  
`<YYYYMMDD>_<TYPE>__<TopicName>.md`  

Example:  
`20250615_SERMON__CovenantPeopleKingdomAssignment.md`

Each begins with YAML front matter:

```yaml
---
title: "Why Covenant Matters"
topic: "Covenant"
type: "Teaching"
date: 2025-06-15
status: Published
---
```

- [Naming guidelines ›](docs/naming.md)  
- [Versioning guide ›](docs/versioning.md)

***

## 📏 File and Path Policy

- **Max full path length:** 80 characters  
- **Recommended filename limit:** 50 characters  
- **Folder naming:** short-kebab-case, max 5 words  
- **Reserved prefixes:**
  - `_` = skip automation/export  
  - `DRAFT__` = internal drafts only  
- Automations should validate path length and safe characters before export.

**Standardized path example:**
```
topics/<short-kebab-case-subfolder>/<YYYYMMDD>_<TYPE>__<TopicName>.md
```

Example:
```
topics/biblical-time/20250812_HANDOUT__BiblicalPropheticTime.md
```

***

## 🧰 Scripts & Automation

For merging templates and exporting formats:

- **PowerShell** — [usage ›](docs/exports.md#powershell)  
- **Node.js** — [usage ›](docs/exports.md#nodejs)  
- **Requirements:** Pandoc, wkhtmltopdf, Node 18+ (for JS automation)

***

## 🚀 Project Roadmap

| Phase | Goal                   | Description                                |
| ----- | ---------------------- | ------------------------------------------ |
| 1     | ✅ Repo Foundation      | Markdown workflow, structured exports      |
| 2     | 🧩 Auto Front-Matter    | Scripted metadata setup                    |
| 3     | 🌐 Web Sync             | Auto-publish to website                    |
| 4     | 🧠 Scripture Parsing    | Auto-link Bible references                 |
| 5     | 🕊️ Visuals              | Enhanced icons and design system           |
| 6     | 📦 Backups              | ZIP archiving and retention policy         |
| 7     | 🧱 Path Validation      | Filename/path validator script             |
| 8     | 🏗️ Template Refactor    | Split into HTML/Markdown sets              |
| 9     | 🧭 Index Generator      | Create searchable topic index              |
| 10    | 🪶 Style Enforcement    | Markdown linter & heading auditor          |
| 11    | 🗄️ Topic Metadata       | Build `meta/metadata.yaml` for each folder |
| 12    | 🌐 Publication Pipeline | Auto-build and deploy HTML+PDF site        |

[Full details ›](docs/roadmap.md)

***

## 🙏 Vision Statement

> “We record, refine, and release revelation —  
> so that the Word given to us may bear fruit through teaching, decrees, and discipleship.”  
> — *Organic Harvest Ministries*

***

## 🔗 Additional Resources

- [Style guide ›](docs/styleguide.md)
- [Directory taxonomy ›](docs/naming.md#topics)
- [Template library ›](docs/templates.md)
- [Roadmap ›](docs/roadmap.md)

***

See the /docs/ folder for all supplementary technical guides, references, and developer notes.

***

Would you like me to create a matching revision for **docs/naming.md** next, aligning it with these new rules (path length, kebab-case folder policy,