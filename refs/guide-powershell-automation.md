<link rel="stylesheet" href="../style.css">



![Status: Draft](https://img.shields.io/badge/Status-DRAFT-orange?style=for-the-badge)




Perfect — below you’ll find:  
1️⃣ the **PowerShell + VSCode automation setup** for your mirror-export system (`topics/` → `topics-htm/`),  
2️⃣ a renamed and structured **`refs/`** hierarchy, and  
3️⃣ the proposed **`refs/index.md`** file explaining the folder’s role and scope.  

***

## 🧠 1. PowerShell and VSCode Automation Setup

### File: `tools/export-html.ps1`

```powershell
<#
.SYNOPSIS
  Converts all Markdown files in /topics/ into HTML under /topics-htm/ using Pandoc.

.DESCRIPTION
  Each .md file in /topics/ receives a corresponding .html output
  in /topics-htm/, preserving the folder structure. The script
  ignores drafts and underscore-prefixed folders.
#>

$SourceFolder = "topics"
$OutputFolder = "topics-htm"
$TemplatePath = "templates/html/standard.html"
$CSSPath = "style.css"

if (!(Test-Path $OutputFolder)) {
    New-Item -ItemType Directory -Path $OutputFolder | Out-Null
}

Get-ChildItem -Path $SourceFolder -Recurse -Filter *.md | ForEach-Object {
    if ($_.FullName -notmatch "_sb|_tmp|drafts") {
        $relativePath = $_.FullName.Substring($SourceFolder.Length)
        $outputPath = Join-Path $OutputFolder ($relativePath -replace ".md$", ".html")

        $dir = Split-Path $outputPath
        if (!(Test-Path $dir)) { New-Item -ItemType Directory -Force -Path $dir | Out-Null }

        Write-Host "Converting:" $_.Name "→" $outputPath -ForegroundColor Green
        pandoc $_.FullName -o $outputPath --template=$TemplatePath --css=$CSSPath
    }
}
Write-Host "✅ HTML export completed. Files written to /topics-htm/"
```

**Usage:**  
`.\tools\export-html.ps1`

***

### VSCode Task (optional automation)

File: `.vscode/tasks.json`

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Export Markdown to HTML (Pandoc)",
      "type": "shell",
      "command": "powershell",
      "args": [
        "-ExecutionPolicy",
        "Bypass",
        "-File",
        "./tools/export-html.ps1"
      ],
      "presentation": {
        "reveal": "always",
        "clear": true
      },
      "group": {
        "kind": "build",
        "isDefault": true
      },
      "problemMatcher": []
    }
  ]
}
```

**Command Palette Shortcut:**  
`Ctrl + Shift + P → Run Task → Export Markdown to HTML (Pandoc)`  
or assign a custom keystroke via VSCode keybindings.

***

## 🗂️ 2. Updated Repository Structure

```text
D:.
│   README.md
│   style.css
│   .gitignore
│
├───refs/
│   ├── index.md
│   ├── naming.md
│   ├── roadmap.md
│   ├── pandoc-yaml.md
│   ├── templates.md
│   ├── exports.md
│   └── versioning.md
│
├───topics/
│   ├── biblical-covenant/
│   ├── foolish-cross/
│   ├── music/
│   └── ...
│
├───topics-htm/
│   └── (auto-generated HTML mirror)
│
├───templates/
│   ├── html/
│   ├── markdown/
│   └── includes/
│
├───tools/
│   └── export-html.ps1
│
├───drafts/
└───_sb/
    └── _tmp/
```

