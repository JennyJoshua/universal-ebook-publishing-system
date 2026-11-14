# Universal eBook Publishing System

A reusable, free-first publishing system for producing professional educational and reference eBooks in PDF and EPUB formats.

## Project status

The repository is currently at the architecture/documentation stage. No executable publishing templates, schemas, scripts, tests, or build workflows have been implemented yet. See [PROJECT_CONTEXT.md](PROJECT_CONTEXT.md) for the full project handover, repository audit, decisions, risks, and roadmap.

## Approved direction

- Structured Markdown is the canonical manuscript source.
- LaTeX is the primary PDF typesetting engine.
- EPUB is produced through a separate, coordinated publishing pipeline.
- Canva is used for covers, illustrations, visual learning assets, and promotional materials.
- GitHub is the source of truth for version control, collaboration, and automated builds.

## Scope boundary

This repository contains the reusable publishing system. Individual books, including the PNG Financial Markets eBook, remain in their own repositories and consume this system through a documented integration contract.

## Principles

- Prefer free and open-source tools; no paid service or API is required by the baseline design.
- Keep manuscript content separate from presentation and build tooling.
- Make builds reproducible and outputs accessible.
- Review changes through pull requests; do not publish releases automatically without approval.

## Status

Architecture and implementation planning are in progress. No book manuscript production or publication is authorized by this repository initialization alone.
