# 🗂️ Repository Structure – ehd-kb-ohm

This document explains how the `ehd-kb-ohm` repository is organized and how the main folders work together to support creating, organizing, and exporting ministry resources.

---

## ✝️ Purpose of This Repository

`ehd-kb-ohm` is a working library for:

- Worksheets and handouts for services, classes, and special events  
- Sermon notes and teaching outlines  
- Church documents and covenant/discipleship materials  
- Music-related practice sheets and prompts  

Content is AI‑assisted but curated for real-world use in Organic Harvest Ministries.

---

## 🧱 High-Level Layout

```text
ehd-kb-ohm
├── README.md
├── README_v02.md
├── _sb/
├── drafts/
├── output/
├── refs/
├── style.css
├── templates/
├── tools/
└── topics/
```

At a glance:

- `drafts/` – where new content starts  
- `topics/` – where curated, canonical content lives  
- `output/` – where printable/usable exports go  
- `refs/` – how‑to docs and standards for the repo  
- `templates/` – starting points for new content  
- `tools/` – helper scripts and utilities  
- `_sb/` – scratchbook / maintenance metadata  

---

## ✍️ Drafts Workflow – `drafts/`

`drafts/` is the staging area for new or evolving material.

Characteristics:

- Files are often paired `.html` + `.md` versions of the same handout or document.  
- Filenames usually contain:
  - A date stamp: `YYYYMMDD_`
  - A type: `HANDOUT`, `SERMON`, `TEACHING-OUTLINE`, `CHURCH-DOC`, etc.
  - A descriptive slug: `BiblicalPropheticTime`, `MarriagesStrong`, `FoolishCross`, etc.
- Examples:
  - `20251012_CHURCH-DOC__covenantConduct_addendum_01.md`
  - `ex__20250905_HANDOUT__MarriagesStrong.md`
  - `kingdom_conduct_covenant.md`

Typical usage:

1. Start new teaching or document here using a template.  
2. Iterate until the content is stable.  
3. When “official,” promote a copy into the appropriate `topics/<Topic Name>/` folder and generate outputs.

---

## 📚 Canonical Topics – `topics/`

`topics/` is the primary knowledge structure for this repo. Each subfolder collects all materials for a coherent theme.

Current topic folders include (non‑exhaustive):

- `topics/Biblical Covenant/`
- `topics/Biblical Time/`
- `topics/Decrees/`
- `topics/Foolish Cross/`
- `topics/Jesus Genealogy Prophecy/`
- `topics/Matthew's Kingdom Parables/`
- `topics/Music/`
- `topics/Unsorted Lessons/`

Within each topic folder you will typically see:

- Canonical Markdown sources:
  - `20250615_CHURCH-DOC__RevisedCovenant.md`
  - `20250615_SERMON__CovenantPeopleKindomAssignment.md`
  - `20250615_TEACHING-OUTLINE__WhyCovenantMatters.md`
- Original/unprocessed source variants:
  - `EHD_MINISTRY_20250615__Covenant.orig.md`
- Thematically grouped handouts or outlines:
  - `20250202_HANDOUT__JesusGenealogyProphecy_01.md`
  - `20250814_HANDOUT__JesusGenealogyProphecyCorrected_01.md`
  - `20250511_HANDOUT__BarstoolsToKingdomTools.md`
  - `20250511_HANDOUT__KindomAmbassadorParablesMatt.md`
  - `20250514_HANDOUT__ChordProgressionPracticeSheet.md`
  - `Prompts.txt` (supporting material for Music)

Guideline:

- Treat `topics/` as the **source of truth** for each theme.  
- Drafts that become part of ongoing teaching should be copied here and maintained here going forward.

---

## 🖨️ Outputs – `output/`

`output/` contains exported/ready‑to‑use artifacts:

- PDF handouts for printing  
- HTML exports for web, slides, or teleprompter use  

Examples:

- `20250202_HANDOUT__JesusGenealogyProphecy_01.01.pdf`
- `20250511_HANDOUT__BarstoolsToKingdomTools.pdf`
- `20250514_HANDOUT__ChordProgressions_01.html`
- `20250615_CHURCH-DOC__RevisedCovenant.html`
- `20250615_SERMON__CovenantPeopleKindomAssignment.html`

Conventions:

- Export filenames generally mirror the corresponding source in `topics/` or `drafts/`.  
- A single logical teaching may have multiple exports (e.g., 3‑page vs 1‑page layouts).

---

## 📖 Reference Docs – `refs/`

`refs/` is the documentation hub for this repository’s process, conventions, and tooling.

Key documents include:

- `exports.md` – how exports are produced and where they go.  
- `guide-powershell-automation.md` – how automation scripts support the repo.  
- `guide-yaml-pandoc.md` – YAML front matter and Pandoc workflow notes.  
- `index.md` – landing/index doc for the `refs/` area.  
- `naming.md` – filename patterns, date codes, and type tags (HANDOUT, SERMON, etc.).  
- `roadmap.md` – planned improvements and future organization.  
- `styleguide.md` – writing and formatting guidelines for ministry content.  
- `templates.md` – overview of available templates and when to use each.  
- `versioning.md` – how versions/revisions are tracked (e.g., `_01`, `v-alt0.2`).

This `repo-structure.md` file should be referenced from `refs/index.md` or `README.md` for discoverability.

---

## 🧩 Templates & Tools

### `templates/`

- Holds reusable skeletons/layouts for:
  - Handouts
  - Sermon notes
  - Teaching outlines
  - Church documents
- New content should typically be created by copying a template into `drafts/` or `topics/` and then customizing.

### `tools/`

- Reserved for:
  - PowerShell, Node.js, or other scripts that automate exports, naming, or tree snapshots.
  - Config files used by those scripts.

If tooling grows, document each script briefly in `refs/guide-powershell-automation.md` or a similar guide.

---

## 🧪 Sandbox & Scratch Experiementation Files

### `_sb/`

- A temporary workspace for quick deposits and manipulation. Content here may become permanent later; if kept, migrate it out of this folder. This directory is ignored by git.

### Miscellaneous

- `style.css` – shared styling used by HTML exports.  
- `desktop.ini`, icon files – OS‑specific customization for local folder display.

---

## 🔁 Recommended Content Lifecycle

1. **Ideate and draft**
   - Start in `drafts/` using an appropriate template and naming convention.  

2. **Refine and approve**
   - Iterate in `drafts/` until the content is approved for teaching or distribution.  

3. **Promote to canonical**
   - Move or copy the finished Markdown into the relevant `topics/<Topic Name>/` folder.  
   - Update any cross‑references or indexes as needed.

4. **Export**
   - Generate HTML/PDF versions into `output/` for printing, emailing, or presenting.  

5. **Document and maintain**
   - Update `refs/` docs (naming, exports, styleguide, roadmap) when the process changes.  
   - Use `_sb/` and `tools/` to keep logs and automation in sync.

---

## ✅ Quick Orientation for New Contributors

- Start by reading: `refs/naming.md`, `refs/styleguide.md`, and this `refs/repo-structure.md`.  
- Look in `topics/` to see how mature content is organized.  
- Use `drafts/` + `templates/` for anything new.  
- Export finished content to `output/` and keep the canonical source in `topics/`.  