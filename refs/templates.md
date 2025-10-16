# Templates and Include Tokens

This document explains the design and usage of the template snippets and HTML layouts that form the backbone of consistent formatting and reusable content in this repository.

---

## Markdown Template Snippets

Located in the `_templates/markdown/` folder, these snippets contain reusable text blocks including:

- Handout headers and sermon footers
- Prayer declaration blocks
- Teaching outline intros
- Scripture callouts and decorative sections

By composing documents from small, standardized parts, content creators ensure consistency and accelerate publishing workflows.

---

## Using Includes in Markdown

Snippets are included in Markdown source files using the `{{include ...}}` syntax. For example:

```
{{include _templates/markdown/handout_header.md}}
```

During export, this token is replaced by the contents of the referenced snippet, supporting modular and maintainable documents.

---

## HTML Templates for Export

HTML layout files are stored in `_templates/html/` and define the rendered format for exported documents:

- `handout_template.html`
- `sermon_template.html`
- `teaching_outline_template.html`
- `component_library.html` (for reusable UI elements like callouts, scripture boxes, and icons)

These templates are used by Pandoc during the export process to generate professional-quality output.

---

## Design Philosophy

- Markdown templates serve ministry content creators, allowing rapid drafting and structural consistency.
- HTML templates serve the technical export system, managing document layout and styling.
- Keeping these responsibilities separate promotes flexible customization without disrupting content workflows.

---

*For more detailed examples and troubleshooting, visit the main [README.md](../README.md).*

[Back to README](../README.md)

***
