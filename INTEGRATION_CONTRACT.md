# Book Repository Integration Contract

## Boundary
A book repository owns all book-specific content and approvals. The Universal eBook Publishing System owns reusable schemas, templates, scripts, tests, and CI components.

## Consumer responsibilities
A consuming book repository should contain:
- book metadata
- canonical Markdown manuscript
- book-specific assets and their rights/attribution notes
- research sources, citations, and editorial records
- a pinned publishing-system version
- book-specific build configuration

## System responsibilities
The publishing system provides:
- versioned content and metadata contract
- PDF and EPUB templates/renderers
- validation and QA scripts
- reproducible build instructions
- optional reusable GitHub Actions workflows

## Pinning
Consumers must pin a tagged release or immutable commit SHA. Avoid consuming the system's moving default branch for a publication build.

## Planned integration options
The initial implementation will compare:
1. A Git submodule or vendored pinned copy.
2. A GitHub Actions reusable workflow that checks out the pinned system version.
3. A release archive downloaded by a pinned tag.

The selected approach must work with public repositories and avoid paid services or API keys.

## First consumer
`JennyJoshua/png-financial-markets-ebook` is the intended first book integration candidate. Its existing research and phase-approval workflow remains authoritative. This contract does not authorize changes to that repository, start manuscript production, or advance its current project phase.
