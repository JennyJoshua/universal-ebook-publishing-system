# Universal eBook Publishing System

A reusable, free-first publishing system for producing professional educational and reference eBooks in PDF and EPUB formats.

## Project status

Repository initialized. The system architecture, templates, build pipelines, and quality checks are being developed on a dedicated branch before review.

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
