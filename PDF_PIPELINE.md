# PDF Pipeline

## Role
LaTeX is the primary engine for professional fixed-layout PDF output. Markdown remains the canonical source; LaTeX is a generated intermediate/rendering target, not the place where authors maintain the manuscript.

## Proposed flow
1. Validate book metadata and manuscript entry point.
2. Resolve and validate local assets and references.
3. Convert/normalize Markdown to LaTeX-compatible input.
4. Apply the shared LaTeX class/template and book-specific configuration.
5. Compile with a pinned TeX distribution and required packages.
6. Run PDF checks (file exists, non-zero size, metadata, page count, links where feasible).
7. Produce a preview artifact for human visual review.

## Layout requirements
- Consistent trim/page size, margins, typography, headings, page numbering, headers/footers, captions, tables, callouts, and references.
- Sensible widow/orphan and page-break handling.
- Figures should remain legible at print size.
- Long tables and code blocks must not overflow page boundaries.
- PDF metadata and document language should be set.

## Tooling direction
Evaluate a Markdown-to-LaTeX converter such as Pandoc with a maintained LaTeX template. Pin versions in CI and document local installation. The exact engine (LuaLaTeX or XeLaTeX) and package set will be selected after a clean-environment prototype.

## Verification
The first sample must be compiled from a clean checkout. A successful local compilation in an earlier experiment is a feasibility signal only; it does not yet prove this repository's pipeline or Overleaf compatibility.
