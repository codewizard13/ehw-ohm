# Naming Conventions and Metadata Standards

Uniform naming and metadata ensure your ministry content is organized, searchable, and easy to automate.

---

## File Naming Structure

All files should follow this format:

```
<YYYYMMDD>_<TYPE>__<TopicName>.<ext>
```

Example filenames:

- `20250615_SERMON__CovenantPeopleKingdomAssignment.md`
- `20250812_HANDOUT__BiblicalPropheticTime.md`
- `DRAFT__kingdom_conduct_covenant_SEMBC.md`

---

## Common Type Prefixes

| Type     | Prefix      | Description                                   |
|----------|-------------|-----------------------------------------------|
| Sermon   | SERMON__    | Full sermon manuscripts                       |
| Teaching | TEACHING__  | Teaching notes and explanatory outlines      |
| Handout  | HANDOUT__   | Printed handouts and summaries                |
| Addendum | ADDENDUM__  | Supplementals or commentary                    |
| Draft    | DRAFT__     | Work-in-progress documents                    |

---

## YAML Front Matter

Each Markdown document begins with structured YAML metadata for automation:

```
***
title: "Why Covenant Matters"
topic: "Covenant"
type: "Teaching"
date: 2025-06-15
series: "Kingdom Covenant Series"
scriptures:
  - Genesis 17:1–8
  - Hebrews 8:6–13
status: "Published"
***
```

Fields represent:

- **title:** Official document title
- **topic:** Primary teaching category
- **type:** Document type (Sermon, Teaching, Handout, etc.)
- **date:** Creation or publication date
- **series:** If part of a teaching series
- **scriptures:** List of key Bible references
- **status:** Workflow state (Draft, Published, etc.)

---

## Metadata Files

Topic folders can contain a `meta/metadata.yaml` file summarizing all published works, associated scriptures, or notes for indexing and quick reference.

---

*Following these conventions supports long-term clarity and collaboration.*

[Back to README](../README.md)

***
