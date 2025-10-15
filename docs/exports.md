# Export Scripts and Automation

This document provides detailed information on using the PowerShell and Node.js export scripts that automate conversion of Markdown teaching materials into HTML, PDF, and other formats. These tools are designed to streamline publishing workflows for Organic Harvest Ministries’ teaching library.

***

## PowerShell Script — `Export-Markdown-v2.ps1`

The PowerShell script is a Windows-native tool that:

- Recursively scans all subfolders within `_topics/` for Markdown (`.md`) files.
- Resolves and merges Markdown snippet includes from `_templates/markdown/`.
- Converts merged Markdown files into HTML and PDF using Pandoc with your custom HTML templates.
- Saves output files into a dedicated `exports/` directory inside each topic folder.
- Logs all processing details and errors to the `_output/export_log.txt` file.

### Usage Example

```powershell
cd D:\OrganicHarvestDocs
.\Export-Markdown-v2.ps1

# Optional: override defaults by specifying root and template path
.\Export-Markdown-v2.ps1 -Root "D:\OrganicHarvestDocs" -TemplateHtml "D:\OrganicHarvestDocs\_templates\html\handout_template.html"
```

***

## Node.js Script — `export-markdown-v2.js`

The Node.js script offers a cross-platform alternative with similar functionality:

- Compatible with Windows, macOS, and Linux.
- Requires Node.js 18+ installed alongside Pandoc and wkhtmltopdf.
- Handles Markdown merging, snippet inclusion, and exports to HTML and PDF.
- Logs actions and errors to the same log file `_output/export_log.txt`.

### Usage Example

```bash
node export-markdown-v2.js --root "D:\OrganicHarvestDocs"

# Optional parameters:
# --templateHtml "D:\OrganicHarvestDocs\_templates\html\sermon_template.html"
# --templateMdDir "D:\OrganicHarvestDocs\_templates\markdown"
```

***

## Requirements

To use either script, ensure the following are installed and their executables are accessible via your system PATH environment variable:

- [Pandoc](https://pandoc.org/installing.html): Required for format conversions.
- [wkhtmltopdf](https://wkhtmltopdf.org/): Used for PDF generation (can be replaced with compatible PDF engine).
- Node.js 18+ (required only for the Node.js export script).

***

## Troubleshooting & Support

- For detailed script internals and common troubleshooting tips, refer to the main [README.md](../README.md).
- Check `_output/export_log.txt` for errors or warnings after running scripts.
- Contact the repository maintainer for further support or to request script enhancements.

***

*This document is part of the Organic Harvest Ministries teaching materials repository and is maintained to support smooth digital publishing workflows.*

[Back to README](../README.md)

***