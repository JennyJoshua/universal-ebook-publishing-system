# Accessibility and Publication QA

## Content checks
- Heading levels are logical and sequential.
- Links use meaningful text.
- Images have meaningful alternative text or are explicitly decorative.
- Tables have captions or clear context and simple header relationships.
- Colour is not the only carrier of meaning.
- Language and metadata are present.
- Footnotes, citations, and references remain understandable in reading order.

## PDF checks
- Text is selectable/searchable where expected.
- Reading order and document language are set where supported.
- Bookmarks or equivalent navigation are present.
- Contrast, font size, figure legibility, margins, and clipping are reviewed.
- Links and references are usable.
- Inspect representative pages and every unusual layout.

## EPUB checks
- EPUB package validates.
- Navigation document and reading order are correct.
- Text reflows at different font sizes and screen widths.
- Images scale without clipping.
- No fixed-page assumptions or horizontal scrolling for ordinary text.
- Metadata, language, cover, and identifier are correct.

## Human review gate
Automated checks cannot establish editorial quality, factual accuracy, or full accessibility. A human must review representative output pages and EPUB reading behaviour before publication.

## Release checklist
- [ ] Manuscript editorial approval recorded by book owner.
- [ ] Facts, citations, permissions, and image rights checked.
- [ ] PDF generated and visually reviewed.
- [ ] EPUB generated and validated.
- [ ] Metadata and version number checked.
- [ ] Accessibility checklist reviewed.
- [ ] Release artifacts and source commit identified.
- [ ] Explicit owner approval obtained before publication.
