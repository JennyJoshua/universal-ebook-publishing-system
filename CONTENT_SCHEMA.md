# Content and Metadata Contract

## Canonical source
The canonical manuscript is UTF-8 Markdown. Content must not be authored separately for PDF and EPUB except for documented format-specific exceptions.

## Book metadata
Each book supplies a machine-readable `book.yml` with, at minimum:
- `title`
- `author` (string or list)
- `language` (BCP 47 language tag, e.g. `en`)
- `identifier` (stable book identifier; use a placeholder only in examples)
- `description`
- `publisher` (optional)
- `publication_date` (optional until approved)
- `series` and `series_position` (optional)
- `rights` / licence statement
- `subject` (list)
- `cover_image` (optional path)
- `manuscript_entry` (path to the Markdown entry point)

Exact requiredness and validation rules will be encoded in a versioned schema during implementation.

## Manuscript conventions
- Use one top-level title per book and a consistent chapter heading level.
- Use semantic heading levels in order; do not choose headings solely for visual size.
- Use Markdown lists, tables, blockquotes, and fenced code where semantically appropriate.
- Use relative paths for local images and other assets.
- Every informative image must have meaningful alternative text; decorative images must be marked appropriately in format-specific output.
- Give tables a clear heading/caption and avoid complex merged-cell layouts.
- Use descriptive link text.
- Use stable identifiers for cross-references where supported.
- Citations and bibliography format must be consistent within a book.

## Format-specific exceptions
A book may provide optional PDF or EPUB overrides only when a genuine format limitation requires them. Overrides must be documented, minimal, and must not fork the whole manuscript.

## Example structure
```text
book-project/
  book.yml
  manuscript/
    index.md
    chapters/
      01-introduction.md
      02-topic.md
  assets/
    cover.png
    figures/
  references/
    bibliography.yml
```

This is a proposed contract; schema details and supported extensions are not considered implemented until validated by tests.
