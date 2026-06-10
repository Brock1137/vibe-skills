---
name: pdf-navigator
description: Use this skill whenever the user needs to read, extract, search, or navigate a PDF file. Triggers on requests like "read this PDF", "find X in the PDF", "what's on page N", "search the PDF for", "how many pages", or any task that requires getting content out of a PDF document. Always use pdf.exe to interact with PDF files rather than attempting to read them directly.
---

# PDF Navigator

Use the `pdf.exe` tool bundled with this skill to interact with PDF files. The executable is located at the same directory as this SKILL.md.

## Commands

### Count pages
```
pdf.exe page-count <file_path>
```

### Extract a specific page (1-indexed)
```
pdf.exe get-page <file_path> <page_number>
```

### Search for text across all pages
```
pdf.exe search <file_path> "<query>"
pdf.exe search <file_path> "<query>" --snippet-chars 400
```
`--snippet-chars` controls how much context surrounds each match (default: 200).

## Navigating an unknown PDF

When asked to work with a PDF you haven't seen before:
1. Run `page-count` to know the document's size
2. Use `search` to jump directly to relevant content
3. Use `get-page` to read specific pages when you need full context

## Notes

- Paths can be absolute or relative to the current working directory
- `get-page` returns raw extracted text — layout may not be preserved
- `search` is case-insensitive and returns snippets for every match on every page
- If a page returns empty text, the PDF may be image-based (scanned) and not machine-readable
