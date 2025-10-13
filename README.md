# ✝️ Organic Harvest Ministries — Teaching & Handout Repository

> **Markdown-first, Spirit-led document system** for sermons, outlines, decrees, and handouts.
> Designed for clarity, reusability, and Kingdom excellence.

---

## 📖 Purpose

This repository organizes all ministry teaching materials into a **structured, version-controlled library**.
Each file begins as a **Markdown (.md)** document — our *living source of truth* — and can be exported to **HTML**, **PDF**, or **DOCX** for printing or web publishing.

This workflow supports:

* 🔹 Fast drafting and revision
* 🔹 Consistent formatting across topics
* 🔹 Reuse of ministry snippets and templates
* 🔹 Automated export for sermons, classes, or online archives

---

## 🗂️ Folder Structure Overview

```
D:.
│   README.md
│   style.css
│
├───_templates/
│   ├───markdown/
│   │       handout_header.md
│   │       teaching_outline_intro.md
│   │       sermon_footer.md
│   │       prayer_declaration_block.md
│   │
│   └───html/
│           handout_template.html
│           sermon_template.html
│           teaching_outline_template.html
│           component_library.html
│
├───_drafts/
│       DRAFT__kingdom_conduct_covenant_SEMBC.md
│       EHD_MINISTRY_20250615__Covenant.orig.md
│
├───_output/
│   ├───html/
│   ├───pdf/
│   ├───docx/
│   ├───site/
│   └───export_log.txt
│
├───Covenant/
│   ├───handouts/
│   │       20250615_HANDOUT__CovenantPeopleKingdomAssignment.md
│   │       20250615_HANDOUT__CovenantPeopleKingdomAssignment.html
│   │
│   ├───sermons/
│   │       20250615_SERMON__CovenantPeopleKingdomAssignment.md
│   │
│   ├───teachings/
│   │       20250615_TEACHING__WhyCovenantMatters.md
│   │
│   ├───addenda/
│   │       20251012_ADDENDUM__CovenantConduct_01.md
│   │       20251012_ADDENDUM__CovenantConduct_01.html
│   │
│   └───exports/
│           20250615_SERMON__CovenantPeopleKingdomAssignment.html
│           20250615_SERMON__CovenantPeopleKingdomAssignment.pdf
│
├───BiblicalTime/
│   │   20250812_HANDOUT__BiblicalPropheticTime.md
│   │   20250812_HANDOUT__BiblicalPropheticTime.html
│
├───Decrees/
│   │   20250905_HANDOUT__MarriagesStrong.md
│   │   20250905_HANDOUT__MarriagesStrong.html
│   │   20250905_HANDOUT__MarriagesStrong.pdf
│
├───FoolishCross/
│   │   20250907_HANDOUT__FoolishCross.md
│   │   20250907_HANDOUT__FoolishCross.html
│
├───JesusGenealogyProphecy/
│   │   20250202_HANDOUT__JesusGenealogyProphecy_01.md
│   │   20250727_HANDOUT__JesusGenealogyProphecy_01_3pp.pdf
│   │   20250814_HANDOUT__JesusGenealogyProphecyCorrected_01.md
│
├───MatthewKingdomParables/
│   │   20250511_HANDOUT__BarstoolsToKingdomTools.md
│   │   20250511_HANDOUT__KingdomAmbassadorParablesMatt.md
│
├───Music/
│   │   20250514_HANDOUT__ChordProgressionPracticeSheet.md
│   │   20250514_HANDOUT__ChordProgressions_01.md
│   │   Prompts.txt
│
└───Unsorted/
```

---

## 🧭 Workflow Summary

### ✍️ Step 1: Draft in Markdown

All original writings are Markdown (`.md`) files.
Each document begins with YAML **front matter** for easy automation:

```yaml
---
title: "Why Covenant Matters"
topic: "Covenant"
type: "Teaching"
date: 2025-06-15
series: "Kingdom Covenant Series"
scriptures:
  - Genesis 17:1–8
  - Hebrews 8:6–13
status: "Published"
---
```

### 🧩 Step 2: Use Markdown Templates (optional)

Re-use ministry-standard sections from `_templates/markdown/`:

```markdown
{% include "../_templates/markdown/handout_header.md" %}

# Why Covenant Matters
We are covenant people, called to reveal the Kingdom...

{% include "../_templates/markdown/sermon_footer.md" %}
```

### 🪄 Step 3: Auto-Export to HTML/PDF

Run the PowerShell export script:

```powershell
cd D:\OrganicHarvestDocs
.\Export-Markdown.ps1
```

This will:

* Convert all `.md` to `.html` and `.pdf`
* Save them to `/exports/` within each topic folder
* Log all actions in `_output/export_log.txt`

### 🧱 Step 4: Style & Publish

`style.css` defines consistent visual presentation.
Use `_output/site/` as a staging area for your public archive or church website.

---

## 🧰 PowerShell Export Script

The script that powers the conversion is stored as:

```
Export-Markdown.ps1
```

It:

* Detects all `.md` files across topic folders
* Inserts Markdown snippets (from `_templates/markdown/`)
* Uses Pandoc + your chosen HTML templates to create `.html` and `.pdf` versions
* Logs success/errors to `_output/export_log.txt`

---

## 🪶 Example Command Flow

```powershell
# 1. Draft your Markdown file
notepad .\Covenant\teachings\20250615_TEACHING__WhyCovenantMatters.md

# 2. Export
.\Export-Markdown.ps1

# 3. View your HTML output
start .\Covenant\exports\20250615_TEACHING__WhyCovenantMatters.html
```

---

## 🧱 Template Philosophy

| Template Type                            | Format  | Purpose                                                          |
| ---------------------------------------- | ------- | ---------------------------------------------------------------- |
| `_templates/markdown/`                   | `.md`   | Textual components (headers, footers, declarations) for drafting |
| `_templates/html/`                       | `.html` | Structural layouts for Pandoc export                             |
| `_templates/html/component_library.html` | `.html` | Reusable UI snippets (callouts, scripture boxes, etc.)           |

Markdown templates serve *content creators*,
HTML templates serve *the export/rendering system*.

---

## 🧩 Naming Conventions

| Type     | Prefix       | Example                                               |
| -------- | ------------ | ----------------------------------------------------- |
| Sermon   | `SERMON__`   | `20250615_SERMON__CovenantPeopleKingdomAssignment.md` |
| Teaching | `TEACHING__` | `20250615_TEACHING__WhyCovenantMatters.md`            |
| Handout  | `HANDOUT__`  | `20250812_HANDOUT__BiblicalPropheticTime.md`          |
| Addendum | `ADDENDUM__` | `20251012_ADDENDUM__CovenantConduct_01.md`            |
| Draft    | `DRAFT__`    | `DRAFT__kingdom_conduct_covenant_SEMBC.md`            |

---

## 🧾 Versioning & File History

* Use `v02`, `v03` suffixes for internal revisions.
* Each major topic folder may include a `meta/metadata.yaml` for listing published works, associated scriptures, or notes.

---

## 🚀 Future Improvements / Project Roadmap

| Phase       | Goal                             | Description                                                                            |
| ----------- | -------------------------------- | -------------------------------------------------------------------------------------- |
| **Phase 1** | ✅ *Repository Foundation*        | Markdown-first workflow with structured exports.                                       |
| **Phase 2** | 🧩 *Auto Front-Matter Injection* | Script enhancement to detect and insert default YAML metadata.                         |
| **Phase 3** | 🌐 *Web Sync Deployment*         | Generate `_output/site/` and auto-publish to `organicharvestministries.org/resources`. |
| **Phase 4** | 🧠 *Scripture Parsing Engine*    | Auto-detect and hyperlink Bible references.                                            |
| **Phase 5** | 🕊️ *Visual Enhancements*        | Add shadcn-styled callouts and iconography for spiritual themes.                       |
| **Phase 6** | 📦 *Archival Automation*         | Weekly ZIP backup of `/exports/` with datestamps.                                      |

---

## 🙏 Vision Statement

> “We record, refine, and release revelation —
> so that the Word given to us may bear fruit through teaching, decrees, and discipleship.”
> — *Organic Harvest Ministries*

---


