# EPUB Pipeline

## Role
EPUB is a separate reflowable output pipeline generated from the same canonical Markdown manuscript. It is not a conversion of the finished PDF.

## Proposed flow
1. Validate metadata and Markdown structure.
2. Convert the manuscript to EPUB-compatible XHTML.
3. Package stylesheet, cover, images, navigation, language, identifier, and publication metadata.
4. Run EPUB structural validation.
5. Inspect navigation, reading order, image alternatives, links, and reflow behaviour in a compatible reader.

## Tooling direction
Use Pandoc's EPUB writer as the initial candidate. Add EPUBCheck or an equivalent validator if it can be run freely in local and GitHub Actions environments. Pin versions and record the exact commands.

## EPUB-specific requirements
- Reflowable text; do not force print page dimensions.
- Valid language and unique identifier metadata.
- Navigable table of contents and logical reading order.
- Semantic headings and accessible image alternatives.
- Avoid layout tables and fixed-position content.
- Include a readable stylesheet and useful cover image metadata.

## Important distinction
The PDF and EPUB outputs should be visually related through shared design tokens and assets, but their layouts are intentionally format-specific. Neither output should be treated as the source for the other.
