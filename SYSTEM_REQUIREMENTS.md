# System Requirements

## Purpose
Provide a reusable, free-first workflow for creating professional educational and reference eBooks in PDF and EPUB formats. The system must support multiple books without copying the publishing platform into each book repository.

## Approved product direction
- Canonical manuscript: structured Markdown.
- Print/PDF composition: LaTeX.
- Reflowable EPUB: a separate Markdown-to-EPUB pipeline.
- Visual assets: Canva for covers, illustrations, diagrams, learning graphics, and promotional assets.
- Source of truth: GitHub.

## Users and outputs
The system is intended for authors, educators, editors, and small publishing teams. A book project supplies its manuscript, metadata, references, and approved visual assets; the system produces validated PDF and EPUB outputs.

## Functional requirements
1. Keep book content independent from publishing templates and scripts.
2. Support shared book metadata and a consistent series design system.
3. Build a PDF from Markdown content using LaTeX templates.
4. Build a separate reflowable EPUB from the same canonical Markdown content.
5. Support front matter, chapters, headings, lists, tables, figures, captions, citations, callouts, glossary entries, and appendices.
6. Validate required metadata, internal links, image references, and output files.
7. Provide a repeatable local build and an optional GitHub Actions build.
8. Keep generated files out of source directories unless explicitly designated as release artifacts.
9. Document how an independent book repository consumes a pinned version of this system.

## Quality requirements
- Reproducible builds with documented tool versions.
- Accessible structure: semantic headings, meaningful link text, image alternatives, readable contrast, and navigable EPUB contents.
- Print-aware PDF layout and reflow-friendly EPUB layout.
- Clear error messages and actionable validation reports.
- No mandatory paid services, API keys, or proprietary authoring tools.

## Non-goals for the first implementation
- Full online authoring/editor application.
- Automated factual research or legal/financial fact-checking.
- Automated distribution to commercial bookstores.
- Dependence on Canva or Overleaf accounts to run the core build.
- Automatic publication or release without owner approval.

## Acceptance criteria for the first usable release
- A sample book builds to PDF and EPUB from one Markdown manuscript source.
- Both outputs include title, author, language, publication metadata, and navigable contents.
- A validation command catches missing required metadata and broken local asset references.
- Build instructions work from a clean checkout.
- The integration contract explains how a separate book repository pins and invokes the system.
