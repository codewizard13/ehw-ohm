<div align="center">

<img src="_pix/logos/logo-ehw-kb-h32.png" alt="Eric Hepperle Designs Logo" width="120"/>

# ✝️ Organic Harvest Ministries Knowledge Base  
### 📖 Worksheets, Sermons, Teaching Resources

_Worksheets, sermon notes, and ministry resources (AI-assisted) for teaching, discipleship, and church life._

[🌐 erichepperle.com](https://erichepperle.com) • [📘 License](#⚖️-license) • [🕊️ About](#🧭-overview)

</div>

***

## 🧭 Overview

This repository houses **Organic Harvest Ministries’** sermon notes, handouts, and discipleship materials — built and managed by **Eric Hepperle Designs**. It’s organized so church leaders and volunteers can quickly find, update, or print resources for Sunday services, classes, or study groups.  

Everything here stays human-readable and portable — Markdown for editing, HTML for preview, and PDF for printing.

***

## 📂 Repository Structure

| Folder / Path | Description |
| ------------- | ----------- |
| `_pix/` | Logos, screenshots, and other static visuals used across documents or READMEs. |
| `drafts/` | Work‑in‑progress handouts, sermons, and church documents. Draft filenames include date, type (HANDOUT, SERMON, etc.), and a short title. |
| `output/` | Final HTML/PDF exports — print‑ready or shareable files. Usually paired with a matching draft or topic version. |
| `topics/` | Organized, canonical content grouped by teaching theme (e.g., Covenant, Music, Biblical Prophecy). Each topic folder acts as the main source of truth. |
| `refs/` | Repo documentation and guides: naming rules, export how‑tos, style guide, roadmap, templates overview, and workflow explanations. |
| `templates/` | Base layouts for new content — use these to start new handouts or sermon outlines. |
| `tools/` | Optional scripts and utilities that automate exports or simplify file management. |
| `style.css` | Shared visual styling for exported HTML handouts. |
| `desktop.ini` | Windows icon/metadata file (safe to ignore when cloning). |

***

## 📚 Topics Overview

The `topics/` directory is the primary way to navigate teaching content. Each subfolder represents a coherent theme with one or more linked handouts or outlines.

| Topic Folder | Example Contents |
| ------------ | ---------------- |
| `Biblical Covenant/` | Church document, sermon, and teaching outline for covenant (e.g., `RevisedCovenant`, `CovenantPeopleKindomAssignment`, `WhyCovenantMatters`). |
| `Biblical Time/` | Handouts related to prophetic or biblical time (e.g., `BiblicalPropheticTime`). |
| `Decrees/` | Decree‑oriented materials such as marriage decrees and covenantal declarations. |
| `Foolish Cross/` | Handouts focused on "Foolishness of the Cross" and related teaching. |
| `Jesus Genealogy Prophecy/` | Jesus' genealogy and prophecy handouts, including corrected/updated versions. |
| `Matthew's Kingdom Parables/` | Materials on Matthew's kingdom parables (e.g., "Barstools to Kingdom Tools", "Kingdom Ambassador Parables"). |
| `Music/` | Music‑related worksheets (chord progressions, practice sheets) and supporting prompt notes. |
| `Unsorted Lessons/` | Holding area for lessons not yet assigned to a primary topic folder. |

When promoting a draft to "canonical," move or copy it under the appropriate `topics/<Topic Name>/` folder so that topic folders remain the source of truth.

---

## 🧩 References, Templates & Tools

These folders support the production workflow for all ministry content in this repository.

| Folder | Role |
| ------ | ---- |
| `refs/` | Documentation hub (exports, automation, YAML/Pandoc guide, naming conventions, roadmap, styleguides, templates, versioning strategy). Start here when you need "how this repo works" information. |
| `templates/` | Base layouts for handouts, sermons, teaching outlines, and docs. Use these as the starting point for new content in `drafts/` and later promote to `topics/`. |
| `tools/` | Scripts, utilities, or configuration used to automate exports, manage filenames, or integrate with your broader tooling. |
| `_sb/` | Log and scratch area: diffs, git logs, and tree snapshots to track change history beyond standard VCS views. |

---

## 📝 Recommended Workflow

1. **Draft** new material inside `drafts/` using a starter from `templates/`.  
2. **Preview or export** it to HTML and PDF into `output/`.  
3. **Finalize/promote** completed documents by dropping them into `topics/<Topic>/`.  
4. **Maintain** workflow consistency by updating reference docs inside `refs/` as your process evolves.  

👉 For detailed roadmap or process planning, check out   [`refs/roadmap.md`](refs/roadmap.md)

***

## 🔗 Additional Resources

If you’re looking for standards and internal documentation, explore the `refs/` folder:

- [`styleguide.md`](refs/styleguide.md) — Formatting rules and Markdown conventions.  
- [`templates.md`](refs/templates.md) — Description of document types and layouts.  
- [`roadmap.md`](refs/roadmap.md) — Current goals and upcoming repo improvements.  

These documents cover the references previously listed under this section, so this version avoids redundancy.

***

## ⚖️ License

This repository is licensed under a standard open source license (e.g., MIT, Apache 2.0) or ministry‑specific terms. See the [LICENSE file](LICENSE) for details.

## 🙏 Acknowledgments

Built with love for ministry using GitHub, Markdown, Pandoc, and AI‑assisted content generation.

---
