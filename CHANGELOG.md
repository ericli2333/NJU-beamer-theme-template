# Changelog

## [v0.3.0] - 2026-10-29

### Added

- `nju-cite.sty`: natbib author-year citations (ICLR-style round/semicolon),
  robust `\citet`/`\citep`, gold citations and automatic brief footnotes.
- `make_shortrefs.py`: generates brief footnote text from a `.bib` file.
- `iclr2027_conference.bst`: reference formatting with blue paper titles and
  gold venue names.
- Citation examples in `presentation.tex`, `demo.tex` and `articlereport.tex`.

### Changed

- Removed the `biblatex`/`footcite` setup from the examples.
- README documents the citation workflow and build command.

## [v0.2.0] - 2026-10-29

### Changed (presentation mode)

- Refreshed the top section banner: 9 pt label, 0.60 cm dark bar, gold rules and section dots.
- Enlarged the frame title to 15 pt in a 4.4 ex bar; title and logo are vertically centred.
- Reworked the footer: 9 pt text in a 5.2 ex bar, background covers the text, date padded from the block edge; original colours kept.
- Loaded `lmodern` and moved box-badness settings into the theme for a warning-free build.

### Compatibility

- Poster and article-report modes are unchanged.
