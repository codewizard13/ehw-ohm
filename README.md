> ⚠️ **DRAFT VERSION — WORK IN PROGRESS**  
> _This document is under active development and may change substantially._

![Status: Draft](https://img.shields.io/badge/Status-DRAFT-orange?style=for-the-badge)


# ✝️ Organic Harvest Ministries — Teaching & Handout Repository

> **Markdown-first, Spirit-led document system** for sermons, outlines, decrees, and handouts.
> Designed for clarity, reusability, and Kingdom excellence.

---

## 📖 Purpose

A **structured, version-controlled library** for all teaching materials. Each is maintained as Markdown (`.md`), enabling rich revision history, easy export, and ministry-wide clarity.

**Key outcomes:**
- 🔹 Fast drafting and revision  
- 🔹 Consistent, reusable templates  
- 🔹 Automated export to HTML, PDF, DOCX  
- 🔹 [Template formatting details ›](docs/templates.md)

***

## 🗂️ Folder Structure Overview

```text
D:.
│   README.md
│   style.css
│
├───_templates/
├───_drafts/
├───_output/
├───_topics/
│   ├───Covenant/
│   ├───BiblicalTime/
│   ├───Decrees/
│   ├───FoolishCross/
│   ├───JesusGenealogyProphecy/
│   ├───MatthewKingdomParables/
│   ├───Music/
│   └───Unsorted/
```
[More on topical categories ›](docs/naming.md#topics)

***

## 🧭 Workflow Summary

1. **Draft in Markdown** using rich front matter  
2. **Utilize templates** via snippet include tokens  
3. **Auto-export** with supported scripts  
   [Complete script guides ›](docs/exports.md)
4. **Style & publish** using consistent CSS

**Quickstart:**
- Draft: `notepad .\_topics\Covenant\teachings\20250615_TEACHING__WhyCovenantMatters.md`
- Export: `.\Export-Markdown-v2.ps1`
- View: open HTML or PDF in `/exports/` subfolder

***

## 🧰 Scripts & Automation

For merging templates and exporting to multiple formats:
- **PowerShell** — [Detailed usage ›](docs/exports.md#powershell)
- **Node.js** — [Detailed usage ›](docs/exports.md#nodejs)
- **Requirements:** Pandoc, wkhtmltopdf, Node 18+ (if using JS version)

***

## 🧩 Templates & Include Tokens

Use ministry-approved blocks for headers, footers, and declarations:
- **Markdown tokens:**  
  `{{include _templates/markdown/handout_header.md}}`
- **HTML templates:**  
  Available for Pandoc conversion
- [Full template guide ›](docs/templates.md)

***

## 🧱 Naming, Metadata & Versioning

Consistent naming:  
`<YYYYMMDD>_<TYPE>__<TopicName>.md`  
Example: `20250615_SERMON__CovenantPeopleKingdomAssignment.md`

Each starts with YAML front matter:
```yaml
---
title: "Why Covenant Matters"
date: 2025-06-15
status: Published
---
```
- [Naming and frontmatter details ›](docs/naming.md)
- [Versioning best practices ›](docs/versioning.md)

***

## 🚀 Project Roadmap

| Phase | Goal | Description |
|-------|------|-------------|
| 1 | ✅ Repo Foundation | Markdown workflow, structured exports |
| 2 | 🧩 Auto Front-Matter | Scripting metadata insertion |
| 3 | 🌐 Web Sync | Auto-publish to website |
| 4 | 🧠 Scripture Parsing | Bible refs auto-linking |
| 5 | 🕊️ Visuals | Enhanced theming/icons |
| 6 | 📦 Backups | Automated ZIP archiving |

[Full roadmap details ›](docs/roadmap.md)

***

## 🙏 Vision Statement

> “We record, refine, and release revelation —  
> so that the Word given to us may bear fruit through teaching, decrees, and discipleship.”  
> — *Organic Harvest Ministries*

***

## 🔗 Additional Resources

- [Style guide ›](docs/styleguide.md) *(future: tone, wording, formatting rules)*
- [Directory taxonomy ›](docs/naming.md#topics)
- [Template library ›](docs/templates.md)

***

See the `/docs/` folder for all supplementary technical guides, references, and developer notes.