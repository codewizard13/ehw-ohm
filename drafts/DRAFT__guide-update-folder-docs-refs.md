GitHub Copilot

I will not edit files directly here, but below are safe, repeatable steps + a small PowerShell script you can run on Windows to update all occurrences of the old docs name to refs across the repo, a sample of the README change, and the git commands to commit.

Files you might want to inspect after the run:
- README.md
- guide-powershell-automation.md
- guide-yaml-pandoc.md
- naming.md

1) PowerShell script to run (creates a commit-friendly backup and replaces word-boundary "docs" → "refs" in common text files)

```powershell
# Backup + Replace script — run from repository root (Windows PowerShell)
param(
    [switch]$WhatIfRun
)

$backupDir = ".rename-backup-$(Get-Date -Format 'yyyyMMddHHmmss')"
New-Item -ItemType Directory -Path $backupDir | Out-Null

$exts = '*.md','*.html','*.json','*.txt','*.ps1'
$files = Get-ChildItem -Recurse -File -Include $exts

foreach ($f in $files) {
    $content = Get-Content -Raw -LiteralPath $f.FullName
    $new = $content -replace '\bdocs\b','refs'        # replace full-word "docs"
    if ($new -ne $content) {
        Write-Host "Updating $($f.FullName)"
        Copy-Item -LiteralPath $f.FullName -Destination (Join-Path $backupDir $f.Name)
        if (-not $WhatIfRun) {
            Set-Content -LiteralPath $f.FullName -Value $new -Encoding UTF8
        }
    }
}

Write-Host "Done. Backed up modified files to $backupDir"
if ($WhatIfRun) { Write-Host "No files were changed because -WhatIfRun was set." }
```

Usage:
- Inspect first: .\tools\rename-docs-to-refs.ps1 -WhatIfRun
- Run actual changes: .\tools\rename-docs-to-refs.ps1

2) Example change (README.md) — this shows how a snippet is updated. Save edits if you prefer manual changes.

```markdown
...existing code...
- [Template formatting details ›](docs/templates.md)
...existing code...
- [Naming guidelines ›](docs/naming.md)  
- [Versioning guide ›](docs/versioning.md)
...existing code...
## 🔗 Additional Resources

- [Style guide ›](docs/styleguide.md)
- [Directory taxonomy ›](docs/naming.md#topics)
- [Template library ›](docs/templates.md)
- [Roadmap ›](docs/roadmap.md)

See the /docs/ folder for all supplementary technical guides, references, and developer notes.
...existing code...
```

Becomes:

```markdown
...existing code...
- [Template formatting details ›](refs/templates.md)
...existing code...
- [Naming guidelines ›](refs/naming.md)  
- [Versioning guide ›](refs/versioning.md)
...existing code...
## 🔗 Additional Resources

- [Style guide ›](refs/styleguide.md)
- [Directory taxonomy ›](refs/naming.md#topics)
- [Template library ›](refs/templates.md)
- [Roadmap ›](refs/roadmap.md)

See the /refs/ folder for all supplementary technical guides, references, and developer notes.
...existing code...
```

3) Quick git commit after verifying changes

```bash
git add -A
git commit -m "chore: update references from docs/ to refs/ after folder rename"
```

Notes & cautions
- The script uses a full-word regex '\bdocs\b' to avoid accidental replacements inside other words. It will still change any standalone "docs" reference (links, text).
- Review changed files (git diff) before committing.
- If you need more surgical replacements (only in markdown links or only in particular file types), tell me and I’ll provide a tightened regex/variant.

Would you like me to generate a smaller, preview-only diff of expected changes (showing each file and the exact lines that would change)?