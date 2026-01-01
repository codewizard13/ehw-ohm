<link rel="stylesheet" href="../style.css">

# 📘 Naming Conventions and Metadata Standards

Uniform naming and metadata ensure all ministry content remains organized, searchable, and automation-friendly across tools like Pandoc, PowerShell, and Node.js exporters.

***

## 🧩 File Naming Structure

All content files follow this strict format:

```
<YYYYMMDD>_<TYPE>__<TopicName>.<ext>
```

**Examples:**
- `20250615_SERMON__CovenantPeopleKingdomAssignment.md`
- `20250812_HANDOUT__BiblicalPropheticTime.md`
- `DRAFT__KingdomConductPrep.md`

This consistent pattern improves traceability, auto-sorting, and version clarity in exports and repositories.

***

## 📂 Folder and Path Naming Rules

### Primary Folder Policy
Every subject or teaching category resides under `/topics/`, using **short kebab-case folder names** with a **5-word maximum**:

```
topics/<short-kebab-case-subfolder>/<YYYYMMDD>_<TYPE>__<TopicName>.md
```

**Good examples:**
- `topics/biblical-covenant/20250615_TEACHING__WhyCovenantMatters.md`
- `topics/foolish-cross/20250907_HANDOUT__FoolishCross.md`
- `topics/jesus-genealogy-prophecy/20250814_HANDOUT__JesusGenealogyProphecyCorrected_01.md`

### Underscore Prefix Usage
Use `_` prefix only for **system or automation folders**. These are ignored by exports and scripts:
- `_sb/` → sandbox / temporary junk files  
- `_internal/` → internal utilities or logs  

**Do not** prefix folders in `topics/` or `templates/` unless they are deliberately excluded from exports.

### Maximum Path and File Length
To ensure compatibility across systems:
- **Max path length:** 80 characters (full `root/folder/file.ext`)  
- **Recommended filename length:** ≤ 50 characters  
- Keep titles succinct; avoid special characters incompatible with URLs or scripts.

Example:
```
topics/biblical-time/20250812_HANDOUT__BiblicalPropheticTime.md
```
✅ **Length:** 69 characters (within safe limit)

***

## 🧱 Document Type Prefixes

| Type         | Prefix       | Description                              |
| ------------ | ------------ | ---------------------------------------- |
| **Sermon**   | `SERMON__`   | Full sermon manuscripts                  |
| **Teaching** | `TEACHING__` | Outlines or explanatory notes            |
| **Handout**  | `HANDOUT__`  | Printed study guides or reference sheets |
| **Addendum** | `ADDENDUM__` | Supplementary explanations               |
| **Draft**    | `DRAFT__`    | Internal work-in-progress drafts         |

Prefixes determine the export category, appearance, and metadata group.

***

## 🗝️ YAML Front Matter

All Markdown documents begin with YAML metadata compatible with Pandoc and automation scripts.

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

### Field References

| Field          | Purpose                                     |
| -------------- | ------------------------------------------- |
| **title**      | Human-readable document title               |
| **topic**      | Topical category under `/topics/`           |
| **type**       | Matches the prefix (e.g. Sermon, Teaching)  |
| **date**       | Creation or publication date                |
| **series**     | Grouped teaching sequence (optional)        |
| **scriptures** | List of Bible references                    |
| **status**     | Workflow state (`Draft`, `Published`, etc.) |

*Front matter ensures every file can be automatically indexed, styled, or exported.*

***

## 🧾 Metadata Summary Files

Each topic folder can include an optional summary file at:  
`topics/<topic-folder>/meta/metadata.yaml`

This file aggregates every published document in that topic area.

Example:
```yaml
topic: "Covenant"
total_files: 5
published:
  - 20250615_SERMON__CovenantPeopleKingdomAssignment.md
  - 20250615_TEACHING__WhyCovenantMatters.md
  - 20250615_HANDOUT__CovenantConduct.md
scriptures:
  - Genesis 12:1–9
  - Hebrews 8:6
last_updated: 2025-06-30
```

***

## ✅ Summary Checklist

- [x] All filenames include `YYYYMMDD` prefix  
- [x] File names use consistent double underscore pattern (`TYPE__TopicName`)  
- [x] Folders under `/topics/` use **kebab-case** and ≤ 5 words  
- [x] Path length ≤ 80 characters  
- [x] `_` prefixed directories excluded from exports  
- [x] YAML front matter is present in all Markdown files  

***

## 🔗 Cross-References

- [README ›](../README.md)
- [Template formatting ›](templates.md)
- [Export scripts ›](exports.md)
- [Style guide ›](styleguide.md)
- [Roadmap ›](roadmap.md)

***

Would you like me to create a short **sample “validation checklist script”** (PowerShell or Node.js) that enforces these filename