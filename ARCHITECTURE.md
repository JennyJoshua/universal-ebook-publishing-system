# Architecture

## Overview
The publishing system is a reusable toolchain consumed by separate book repositories. It is not the home of any individual book's research or manuscript.

```text
Book repository
  ├── book.yml (metadata and build configuration)
  ├── manuscript/ (canonical Markdown)
  ├── assets/ (approved images, diagrams, fonts where licensing permits)
  └── references/ (bibliography and source notes)
          |
          v
Universal publishing system (pinned version)
  ├── schema and validation
  ├── Markdown preprocessing
  ├── LaTeX PDF template and build
  ├── EPUB packaging and navigation
  ├── accessibility / output checks
  └── build documentation
          |
          v
      PDF + EPUB
          |
          v
  Human review and approved release
```

## Component responsibilities
- **Book repository:** owns manuscript, research, citations, book-specific metadata, and book assets.
- **Content contract:** defines supported Markdown conventions and metadata.
- **Preprocessor:** normalizes content and prepares format-specific inputs without changing the canonical manuscript.
- **PDF renderer:** applies the LaTeX template, page geometry, typography, headers, footers, figures, tables, and print conventions.
- **EPUB renderer:** packages reflowable XHTML, CSS, metadata, navigation, and referenced assets.
- **Validator:** checks metadata, references, links, assets, and generated output structure.
- **GitHub Actions:** runs repeatable checks/builds and stores preview artifacts; publication remains approval-gated.
- **Canva:** optional external visual-production workspace. Exported approved assets are committed to the book repository; Canva is not a runtime dependency.

## Design principles
1. One canonical manuscript; multiple format-specific renderers.
2. Keep content, assets, templates, and tooling separate.
3. Pin system versions in each consuming book project.
4. Prefer deterministic, documented tooling.
5. Fail early with readable validation errors.
6. Keep the core pipeline usable without network services after dependencies are installed.
7. Never silently rewrite author content during a build.

## Repository boundaries
This repository owns reusable schemas, templates, scripts, tests, and workflows. A book repository owns its own research and editorial approvals. Integration must not move or duplicate a book's source material into this repository.

## Initial implementation sequence
1. Stabilize metadata and manuscript conventions.
2. Add a minimal sample project and schema validation.
3. Implement PDF rendering and verify typography/layout.
4. Implement independent EPUB generation from the same Markdown source.
5. Add cross-format and accessibility checks.
6. Add CI preview builds and versioned releases.
7. Pilot integration with the Financial Markets book only after its owner-approved phase allows production integration.
