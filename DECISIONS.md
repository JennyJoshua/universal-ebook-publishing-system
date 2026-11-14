# Architecture Decisions

## Accepted

### D-001 — Separate reusable system repository
The reusable publishing system lives in `JennyJoshua/universal-ebook-publishing-system`. Individual books remain in their own repositories.

### D-002 — Hybrid publishing architecture
- Structured Markdown is the common manuscript source.
- LaTeX is the primary PDF typesetting engine.
- EPUB uses an independent pipeline from the same Markdown source.
- Canva creates visual assets, not the canonical manuscript.
- GitHub is the source of truth and build/release coordination point.

### D-003 — Visual direction
Modern Editorial foundation with selected Illustrated Learning elements (AB).

### D-004 — Series identity
A shared series identity with subject-specific accent colours.

### D-005 — Formats
PDF and EPUB are both required outputs.

### D-006 — Free-first baseline
No paid service, API, or mandatory proprietary authoring platform in the core publishing workflow.

### D-007 — Repository visibility
The reusable system repository is public.

## Deferred
- Exact Markdown extensions and metadata schema.
- LaTeX engine and package set.
- EPUB validator and exact tool versions.
- System CLI interface.
- Consumer integration mechanism.
- Licence selection for the repository and sample assets.
- Final Canva template selection.
- Overleaf compatibility validation.

## Constraints
- No production changes to the Financial Markets book repository are included in this initial system documentation.
- No automatic publication or release without explicit owner approval.
- Figma remains optional and paused; it is not a dependency.
