> ⚠️ **DRAFT VERSION — WORK IN PROGRESS**  
> _This document is under active development and may change substantially._

![Status: Draft](https://img.shields.io/badge/Status-DRAFT-orange?style=for-the-badge)


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


Great — below are two complete, ready-to-run scripts (PowerShell **v2** and **Node.js**) that implement your Markdown-first workflow, **merge Markdown snippets** from `_templates/markdown/` into each source file, and export **HTML + PDF** using Pandoc with your HTML layout templates.

Both scripts:

* Keep Markdown as the source of truth (never overwrite original `.md`).
* Support simple Markdown snippet inclusion using `{{include path/to/snippet.md}}`.
* Write outputs to `...\<topic>\exports\`.
* Log actions to `_output/export_log.txt`.
* Do **not** delete files; they only read & create outputs.

---

## Requirements (common)

1. **Pandoc** installed and on PATH.
   [https://pandoc.org/installing.html](https://pandoc.org/installing.html)
2. **wkhtmltopdf** installed and on PATH (or change PDF engine).
3. For the Node.js script: **Node 18+** installed.

---

## Include Token (how snippets are merged)

In any `.md` file, use:

```
{{include _templates/markdown/handout_header.md}}
```

Relative or absolute paths are both supported. The script replaces the token with the contents of the referenced `.md`. It supports nested includes (but avoid circular includes).

---

# 1) PowerShell Script — `Export-Markdown-v2.ps1`

Save to `D:\OrganicHarvestDocs\Export-Markdown-v2.ps1`

```powershell
<#
.SYNOPSIS
  Export-Markdown-v2.ps1
.DESCRIPTION
  Scans topic folders for .md files, merges markdown snippets from _templates/markdown,
  exports HTML and PDF using Pandoc with HTML templates, and logs results.
.NOTES
  Requirements: Pandoc + wkhtmltopdf on PATH.
#>

param(
    [string]$Root = "D:\OrganicHarvestDocs",
    [string]$TemplateHtml = "",          # If empty uses $Root\_templates\html\handout_template.html
    [string]$TemplateMdDir = "",         # If empty uses $Root\_templates\markdown
    [string]$CssRelativePath = "..\..\style.css"
)

# --- Defaults ---------------------------------------------------------------
if ($TemplateHtml -eq "") { $TemplateHtml = Join-Path $Root "_templates\html\handout_template.html" }
if ($TemplateMdDir -eq "")  { $TemplateMdDir = Join-Path $Root "_templates\markdown" }

$logFile = Join-Path $Root "_output\export_log.txt"
$tempDir = Join-Path $Root "_output\temp_merged"
if (!(Test-Path (Split-Path $logFile))) { New-Item -ItemType Directory -Path (Split-Path $logFile) | Out-Null }
if (!(Test-Path $tempDir)) { New-Item -ItemType Directory -Path $tempDir | Out-Null }

"=== Export started $(Get-Date -Format o) ===" | Out-File $logFile -Append
Write-Host "Export started. Root: $Root" -ForegroundColor Cyan

function Resolve-Includes {
    param(
        [string]$content,
        [string]$baseDir
    )
    # Replace tokens like {{include path/to/snippet.md}}
    $pattern = '\{\{\s*include\s+([^\}]+)\s*\}\}'
    while ($content -match $pattern) {
        $match = [regex]::Match($content, $pattern)
        $incPath = $match.Groups[1].Value.Trim()
        # Resolve relative to baseDir first, then root
        $candidate = $null
        $try1 = Join-Path $baseDir $incPath
        $try2 = Join-Path $Root $incPath
        $try3 = Join-Path $TemplateMdDir $incPath
        if (Test-Path $try1) { $candidate = (Resolve-Path $try1).ProviderPath }
        elseif (Test-Path $try2) { $candidate = (Resolve-Path $try2).ProviderPath }
        elseif (Test-Path $try3) { $candidate = (Resolve-Path $try3).ProviderPath }
        else {
            Write-Host "⚠ Include not found: $incPath (base: $baseDir). Token left as-is." -ForegroundColor Yellow
            $content = $content -replace [regex]::Escape($match.Value), $match.Value
            break
        }
        $incText = Get-Content -Raw -Path $candidate
        # Recursive include resolution
        $incTextResolved = Resolve-Includes -content $incText -baseDir (Split-Path $candidate -Parent)
        $content = $content -replace [regex]::Escape($match.Value), [System.Text.RegularExpressions.Regex]::Escape($incTextResolved)
        # Note: we escaped replacement to preserve markdown special chars; then unescape
        $content = [System.Text.RegularExpressions.Regex]::Unescape($content)
    }
    return $content
}

function Export-File {
    param([string]$mdPath)
    $folder = Split-Path $mdPath -Parent
    $base = [System.IO.Path]::GetFileNameWithoutExtension($mdPath)
    $exports = Join-Path $folder "exports"
    if (!(Test-Path $exports)) { New-Item -ItemType Directory -Path $exports | Out-Null }

    $mergedTemp = Join-Path $tempDir ("$base.merged.md")
    try {
        $raw = Get-Content -Raw -Path $mdPath
        $resolved = Resolve-Includes -content $raw -baseDir $folder

        # Write merged temp file
        $resolved | Out-File -FilePath $mergedTemp -Encoding UTF8

        $htmlOut = Join-Path $exports "$base.html"
        $pdfOut  = Join-Path $exports "$base.pdf"

        # Pandoc commands
        $pandocHtmlCmd = @("pandoc", $mergedTemp, "-s", "-o", $htmlOut, "--template=$TemplateHtml", "--metadata=pagename:$base", "--css=$CssRelativePath")
        $pandocPdfCmd  = @("pandoc", $mergedTemp, "-s", "-o", $pdfOut, "--pdf-engine=wkhtmltopdf")

        # Run HTML
        & pandoc $mergedTemp -s -o $htmlOut --template="$TemplateHtml" --metadata=pagename="$base" --css="$CssRelativePath"
        # Run PDF
        & pandoc $mergedTemp -s -o $pdfOut --pdf-engine=wkhtmltopdf

        "OK: $mdPath -> $htmlOut, $pdfOut" | Out-File $logFile -Append
        Write-Host "✔ Exported: $base" -ForegroundColor Green
    }
    catch {
        "ERROR: $mdPath -> $_" | Out-File $logFile -Append
        Write-Host "❌ Error exporting $mdPath : $_" -ForegroundColor Red
    }
    finally {
        if (Test-Path $mergedTemp) { Remove-Item $mergedTemp -Force }
    }
}

# Collect topic folders (exclude underscored and the output folders)
$topicFolders = Get-ChildItem -Path $Root -Directory | Where-Object {
    $_.Name -notmatch '^_' -and $_.Name -ne 'Unsorted' -and $_.Name -ne '_output'
}

foreach ($folder in $topicFolders) {
    $mdFiles = Get-ChildItem -Path $folder.FullName -Recurse -Filter *.md -File
    foreach ($file in $mdFiles) {
        Export-File -mdPath $file.FullName
    }
}

"=== Export completed $(Get-Date -Format o) ===`n" | Out-File $logFile -Append
Write-Host "All exports complete. Log: $logFile" -ForegroundColor Cyan
```

### Usage (PowerShell)

```powershell
# Run with defaults:
cd D:\OrganicHarvestDocs
.\Export-Markdown-v2.ps1

# Or override root and templates:
.\Export-Markdown-v2.ps1 -Root "D:\OrganicHarvestDocs" -TemplateHtml "D:\OrganicHarvestDocs\_templates\html\handout_template.html"
```

---

# 2) Node.js Script — `export-markdown-v2.js`

Save to `D:\OrganicHarvestDocs\export-markdown-v2.js`

```javascript
#!/usr/bin/env node
/**
 * export-markdown-v2.js
 * Node.js version of export script.
 *
 * Requirements:
 *  - Node 18+
 *  - Pandoc + wkhtmltopdf on PATH
 *
 * Usage:
 *   node export-markdown-v2.js --root "D:\OrganicHarvestDocs"
 */

const fs = require('fs/promises');
const fsSync = require('fs');
const path = require('path');
const { execFile } = require('child_process');
const { argv } = require('process');

function parseArgs() {
  const args = {};
  for (let i = 2; i < argv.length; i++) {
    if (argv[i].startsWith('--')) {
      const key = argv[i].replace(/^--/, '');
      const val = argv[i+1] && !argv[i+1].startsWith('--') ? argv[i+1] : true;
      args[key] = val;
      if (val !== true) i++;
    }
  }
  return args;
}

const args = parseArgs();
const ROOT = args.root ? args.root : path.resolve("D:/OrganicHarvestDocs");
const TEMPLATE_HTML = args.templateHtml ? args.templateHtml : path.join(ROOT, "_templates", "html", "handout_template.html");
const TEMPLATE_MD_DIR = args.templateMdDir ? args.templateMdDir : path.join(ROOT, "_templates", "markdown");
const LOGFILE = path.join(ROOT, "_output", "export_log.txt");
const TEMP_DIR = path.join(ROOT, "_output", "temp_merged");

// ensure dir exists
async function ensureDir(dir) {
  await fs.mkdir(dir, { recursive: true });
}

async function logLine(line) {
  await ensureDir(path.dirname(LOGFILE));
  await fs.appendFile(LOGFILE, line + "\n", "utf8");
}

async function readAllFilesRecursive(dir, ext) {
  const results = [];
  async function readDir(d) {
    const entries = await fs.readdir(d, { withFileTypes: true });
    for (const e of entries) {
      const full = path.join(d, e.name);
      if (e.isDirectory()) await readDir(full);
      else if (e.isFile() && full.endsWith(ext)) results.push(full);
    }
  }
  await readDir(dir);
  return results;
}

async function resolveIncludes(content, baseDir, visited = new Set()) {
  const includeRegex = /\{\{\s*include\s+([^\}]+)\s*\}\}/g;
  let match;
  let out = content;
  while ((match = includeRegex.exec(content)) !== null) {
    const token = match[0];
    const incPathRaw = match[1].trim();
    const candidates = [
      path.resolve(baseDir, incPathRaw),
      path.resolve(ROOT, incPathRaw),
      path.resolve(TEMPLATE_MD_DIR, incPathRaw)
    ];
    let found = null;
    for (const c of candidates) {
      if (fsSync.existsSync(c) && fsSync.lstatSync(c).isFile()) { found = c; break; }
    }
    if (!found) {
      console.warn(`Include not found: ${incPathRaw} (base ${baseDir}) — leaving token as-is.`);
      continue;
    }
    if (visited.has(found)) {
      console.warn(`Circular include detected: ${found}. Skipping to avoid infinite loop.`);
      out = out.replace(token, `<!-- circular-include:${path.basename(found)} -->`);
      continue;
    }
    visited.add(found);
    const incText = await fs.readFile(found, 'utf8');
    const resolvedInc = await resolveIncludes(incText, path.dirname(found), visited);
    visited.delete(found);
    out = out.replace(token, resolvedInc);
  }
  return out;
}

function execPandoc(args) {
  return new Promise((resolve, reject) => {
    const cmd = 'pandoc';
    execFile(cmd, args, (error, stdout, stderr) => {
      if (error) return reject({ error, stdout, stderr });
      resolve({ stdout, stderr });
    });
  });
}

async function exportFile(mdPath) {
  try {
    const folder = path.dirname(mdPath);
    const base = path.basename(mdPath, '.md');
    const exportsDir = path.join(folder, 'exports');
    await ensureDir(exportsDir);
    await ensureDir(TEMP_DIR);

    const raw = await fs.readFile(mdPath, 'utf8');
    const resolved = await resolveIncludes(raw, folder);

    const mergedTempPath = path.join(TEMP_DIR, `${base}.merged.md`);
    await fs.writeFile(mergedTempPath, resolved, 'utf8');

    const htmlOut = path.join(exportsDir, `${base}.html`);
    const pdfOut = path.join(exportsDir, `${base}.pdf`);

    // HTML conversion
    await execPandoc([mergedTempPath, '-s', '-o', htmlOut, `--template=${TEMPLATE_HTML}`, `--metadata=pagename:${base}`, '--css=../../style.css']);

    // PDF conversion using wkhtmltopdf via pandoc
    await execPandoc([mergedTempPath, '-s', '-o', pdfOut, '--pdf-engine=wkhtmltopdf']);

    const okLine = `OK: ${mdPath} -> ${htmlOut}, ${pdfOut}`;
    await logLine(okLine);
    console.log(`✔ ${base}`);
    await fs.rm(mergedTempPath, { force: true });
  } catch (err) {
    const errLine = `ERROR: ${mdPath} -> ${err.error ? err.error.message : err}`;
    await logLine(errLine);
    console.error(`❌ Failed: ${mdPath}`, err);
  }
}

(async function main(){
  await ensureDir(TEMP_DIR);
  await logLine(`=== Export started ${new Date().toISOString()} ===`);
  console.log(`Starting export (root=${ROOT})`);

  const entries = await fs.readdir(ROOT, { withFileTypes: true });
  const topicFolders = entries.filter(e => e.isDirectory() && !e.name.startsWith('_') && e.name !== 'Unsorted' && e.name !== '_output');

  for (const folder of topicFolders) {
    const folderPath = path.join(ROOT, folder.name);
    const mdFiles = await readAllFilesRecursive(folderPath, '.md');
    for (const md of mdFiles) {
      await exportFile(md);
    }
  }

  await logLine(`=== Export completed ${new Date().toISOString()} ===\n`);
  console.log('All exports complete.');
})();
```

### Usage (Node.js)

```powershell
# From PowerShell or cmd:
cd D:\OrganicHarvestDocs
node export-markdown-v2.js --root "D:\OrganicHarvestDocs"

# Optional params:
# --templateHtml "D:\OrganicHarvestDocs\_templates\html\sermon_template.html"
# --templateMdDir "D:\OrganicHarvestDocs\_templates\markdown"
```

---

## Notes & Tips

* **CSS path**: The scripts use `--css ../../style.css` from each `exports` folder. If your layout differs, adjust the `$CssRelativePath` in PowerShell or `--css` in Node script.
* **Templates**: Keep HTML templates in `_templates/html/`. Keep Markdown snippets in `_templates/markdown/`.
* **PDF engine**: If you prefer `wkhtmltopdf`, keep it installed. You can change Pandoc’s `--pdf-engine` option to `weasyprint`, `prince`, or `xelatex` depending on your environment.
* **Safety**: Scripts never remove original `.md` files. Temp files are cleaned up after each file.
* **Large repos**: For many files, run scripts during off-hours or on a machine with enough RAM — Pandoc & PDF rendering can be memory-heavy.
* **Testing**: Test with one small folder first:

  * Copy a topic to `D:\OrganicHarvestDocs\TestTopic\`
  * Put a single `.md` with a `{{include ...}}` token and run the script.

---

## Would you like:

* ✅ I can produce a **PowerShell v2 README snippet** that you can paste into your repo root as `USAGE.md` (short quickstart).
* ✅ Or I can **add ZIP archiving** and an **auto-front-matter checker** to either script (Phase 2 on your roadmap).

Which next enhancement should I add?



---


Excellent — this is the kind of structure that can scale beautifully if the topical organization is right. Let’s **distill your actual topics** from what’s in this directory tree, then identify **major speculative categories** that would fit your teaching and content strategy going forward (based on your prophetic–Kingdom emphasis and the mix of sermon, decree, and handout materials).

---

## 🧭 **Observed Topics (from your current repo)**

Here are the natural topic clusters already present in the folder tree, organized conceptually rather than by file path:

| **Primary Topic**                        | **Focus / Content Summary**                                                                          | **Example File(s)**                                                 |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| **Biblical Covenant**                    | Covenant theology, church member covenant, conduct, covenant purpose and meaning, Kingdom assignment | `RevisedCovenant`, `WhyCovenantMatters`, `kingdom_conduct_covenant` |
| **Biblical Time / Prophetic Chronology** | Understanding God’s timetable, prophetic epochs, dispensations, and biblical calendars               | `BiblicalPropheticTime`                                             |
| **Decrees & Declarations**               | Faith confessions, spoken decrees (esp. for marriage strength, blessings, etc.)                      | `MarriagesStrong`                                                   |
| **The Foolishness of the Cross**         | Christ-centered message contrasting worldly wisdom with divine revelation                            | `FoolishCross`                                                      |
| **Jesus’ Genealogy & Prophecy**          | Messianic lineage, fulfillment of prophecy, divine order of generations                              | `JesusGenealogyProphecy`                                            |
| **Matthew’s Kingdom Parables**           | Parables revealing Kingdom operations and ambassadorial identity                                     | `BarstoolsToKingdomTools`, `KindomAmbassadorParablesMatt`           |
| **Music & Worship Tools**                | Chord sheets, worship theory, instrumental practice materials                                        | `ChordProgressionPracticeSheet`, `ChordProgressions_01`             |
| **Unsorted Lessons**                     | Draft or unclassified materials (placeholder for future categorization)                              | `Unsorted Lessons` folder                                           |

---

## 🔍 **Distilled Topic List (Current Scope)**

1. Covenant & Kingdom Conduct
2. Prophetic Time & Dispensations
3. Faith Decrees & Confessions
4. The Cross & Redemption Wisdom
5. Messianic Genealogy & Prophecy
6. Parables of the Kingdom
7. Music & Worship Development
8. General Teaching / Unsorted

---

## 🧱 **Speculative Additional Major Categories (for future organization)**

These categories are extrapolated from your ministry’s direction (Spirit-filled prophetic Kingdom teaching, covenant life application, and holistic discipleship):

| **Proposed Category**                           | **Purpose / Scope**                                                       | **Example Future Content Ideas**                                                             |
| ----------------------------------------------- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| **Kingdom Foundations**                         | Core doctrines of Kingdom citizenship, authority, purpose, and governance | *The Seven Mountains Mandate, Kingdom Culture vs. Religion, Dominion through Service*        |
| **Prophetic Realms & Spiritual Beings**         | Angels, principalities, Nephilim, thrones, divine councils                | *Understanding Angelic Hierarchies, Giants and Hybrid Bloodlines, Warfare in the Heavenlies* |
| **Church Governance & Discipleship**            | Local church covenant, leadership, member conduct                         | *Fivefold Ministry Roles, Covenant Membership, Kingdom Leadership Principles*                |
| **Faith & Decree Practice**                     | Scriptural declarations, faith language, prophetic intercession           | *Daily Decree Booklets, Prayer Vigils, Healing and Deliverance Confessions*                  |
| **End-Time Timelines & Dispensational Studies** | Larkin-style charts, eschatology, prophetic eras                          | *Daniel’s 70 Weeks, The Church Age, Millennial Reign Studies*                                |
| **Biblical Typology & Symbolism**               | Patterns, shadows, and types across Old and New Testaments                | *Tabernacle Patterns, Joseph as a Type of Christ, Numbers and Colors in Scripture*           |
| **Worship Arts & Prophetic Music**              | Integrating music, art, and prophetic flow in ministry                    | *Sound and Glory, Frequency and Anointing, Healing through Worship*                          |
| **Holistic Kingdom Living**                     | Natural wellness, stewardship, and alignment of body-soul-spirit          | *Temple Health Protocols, Dominion Diet, Spiritual Roots of Sickness*                        |
| **Teaching Templates & Handout Library**        | Ready-to-use sermon/handout structures                                    | *church_handout_markdown.md*, *DRAFT templates for all content types*                        |
| **Ministry Operations & Outreach**              | Branding, giving schedules, missions, online evangelism                   | *Organic Harvest Ministries overview, giving strategies, donor communications*               |

---

## 🗂️ **Suggested Top-Level Directory Structure (Reorganized Vision)**

```
D:.
│
├── Kingdom Foundations
├── Covenant Life & Church Conduct
├── Prophetic Timelines & Dispensations
├── Prophetic Realms & Spiritual Beings
├── Decrees & Faith Confessions
├── Parables & Teachings of Jesus
├── The Cross & Redemption
├── Worship & Music
├── Holistic Kingdom Living
├── Ministry Operations
└── Templates & Shared Components
```

---

## 🚀 **Future Improvements / Roadmap**

1. **Standardize File Naming:** `<YYYYMMDD>_<TYPE>__<TopicName>.<ext>` is excellent — keep it consistent.
2. **Tagging System:** Use frontmatter tags (`topics: [covenant, kingdom, prophecy]`) in Markdown for easy programmatic sorting.
3. **Metadata Extraction:** Create an index generator to produce a `SUMMARY.md` or searchable catalog.
4. **Teaching Mode Labels:** Tag each file as `Sermon`, `BibleStudy`, or `PrayerVigil` for quick retrieval.
5. **“Unified Handout Format” Template:** Standardize styling, fonts, and scripture display format.
6. **Versioned Repository for Series:** e.g., `Series_JesusGenealogyProphecy_v1.1` for successive teaching cycles.

---

Would you like me to **generate a visual taxonomy chart or table** (e.g., a “Kingdom Teaching Topics Map”) from this proposed categorization? It could show relationships (Covenant → Kingdom Conduct → Decrees → Prophetic Manifestation) for use in documentation or website navigation.


---


Great question — it’s subtle but important. Let’s break it down clearly:

---

## **1. Covenant Life / Church Conduct**

**Focus:** The spiritual, moral, and relational framework for members of the Body of Christ.
**Purpose:** Guides **how believers live, relate, and function** in alignment with God’s Kingdom covenant.

**Key Aspects:**

* **Personal and corporate obedience**: Walking in God’s Word and covenant promises.
* **Spiritual responsibilities**: Prayer, worship, stewardship of gifts, discipleship.
* **Church conduct**: Membership covenants, ethical behavior, social media use, interpersonal relationships.
* **Kingdom alignment**: Understanding one’s role in God’s Kingdom and applying biblical principles to daily life.
* **Teaching tools**: Sermons, handouts, outlines, covenant agreements, behavioral guidelines.

**Example Files:**

* `kingdom_conduct_covenant.md`
* `20250615_CHURCH-DOC__RevisedCovenant.md`
* `20250907_HANDOUT__FoolishCross.md`

---

## **2. Ministry Operations**

**Focus:** The **practical, administrative, and strategic side** of running a ministry or church.
**Purpose:** Ensures that the ministry functions efficiently, reaches people effectively, and sustains itself financially and organizationally.

**Key Aspects:**

* **Financial stewardship & donations**: Giving schedules, accounting, fund allocation.
* **Branding and outreach**: Websites, email campaigns, domain management, social media strategy.
* **Event and program management**: Scheduling sermons, Bible studies, prayer vigils, workshops.
* **Content management**: Organizing teaching materials, templates, handouts, and series archives.
* **Operational governance**: Policies, leadership structures, reporting mechanisms.

**Example Files:**

* (Prospective — not explicitly in your current repo yet)
* Donor schedules, `Prompts.txt` for content generation, website templates, email templates.

---

### **✅ Key Differentiation**

| **Aspect**          | **Covenant Life**                                        | **Ministry Operations**                                                |
| ------------------- | -------------------------------------------------------- | ---------------------------------------------------------------------- |
| **Core question**   | “How should we live and serve as God’s covenant people?” | “How do we organize, fund, and deliver ministry effectively?”          |
| **Primary content** | Doctrine, conduct, spiritual growth, discipleship        | Logistics, governance, administration, outreach tools                  |
| **Audience**        | Members, disciples, believers                            | Leaders, staff, volunteers, ministry managers                          |
| **Output examples** | Handouts on covenant, sermons, teaching outlines         | Donation schedules, email campaigns, website content, program planning |

---

💡 **In short:**
Covenant life is **spiritual formation and alignment**, ministry operations is **practical implementation and management**. One shapes the hearts of God’s people; the other shapes the systems that enable God’s work to reach the world.

---

If you want, I can **map all your current files into these two categories** to make it crystal clear which folder belongs where, and show which ones might bridge both worlds. This would help you finalize the repo structure. Do you want me to do that?


----


