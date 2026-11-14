# Build and Release Workflow

## Development principles
- Keep the core pipeline free and usable without external APIs.
- Pin tool versions and dependencies.
- Separate pull-request preview builds from publication releases.
- Never deploy or publish a book automatically as a side effect of a routine commit.

## Planned commands
The exact CLI names will be finalized with the first working implementation. Intended interface:

```sh
# Validate metadata and manuscript
publisher validate --project .

# Build both formats
publisher build --project . --formats pdf,epub

# Build one format
publisher build --project . --formats pdf
publisher build --project . --formats epub
```

These are interface proposals, not commands implemented yet.

## Local build
A clean-checkout setup guide will document the supported operating system, runtime, TeX distribution, Pandoc version, EPUB validator, and installation steps. Avoid requiring desktop GUI tools for routine builds where command-line equivalents exist.

## GitHub Actions plan
- Pull requests: validate source and build preview PDF/EPUB artifacts.
- Main branch: run tests and build verification.
- Version tags: prepare release artifacts but require explicit approval before public publication.
- Cache dependencies where safe; do not cache generated output in a way that hides stale builds.

## Versioning
Use semantic versioning for the reusable system once the public interface is stable. Book repositories should pin a release tag or immutable commit rather than tracking a moving branch for production builds.

## Release approval
A successful CI build is not authorization to publish. A human owner reviews outputs and explicitly approves each publication release.
