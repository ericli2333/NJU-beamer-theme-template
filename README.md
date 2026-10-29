# NJU Presentation Theme

This is a beamer template for Nanjing University (NJU) presentation. It is adapted from the unofficial FSU Beamerposter & Presentation Theme by Rafiq Islam.

original repository: [FSU Beamer](https://github.com/mrislambd/FSU-math-poster-template)

## Changes Made
- Added NJUPurple color and adjusted background and text colors accordingly.
- Replaced FSU logo with NJU logo.
- Adjusted document class and font settings to better suit NJU presentation style.
- Replaced `biblatex` with `natbib` author-year citations in the ICLR style (round parentheses, semicolon separator).
- Added `nju-cite.sty`: robust `\citet`/`\citep`, gold citations, and an automatic brief footnote on the citation page.
- Added `make_shortrefs.py` and `iclr2027_conference.bst`; paper titles are blue, venue names gold, URLs keep their default style.
- Add a new frame before each section and subsection for better structure.
- Change font settings of math and Chinese
- Change the blocking enviroments to `tcolorbox`
- Add logo on the top of each slide

## Presentation Mode Refresh (v0.2.0)

This release refreshes the presentation layout:

- A compact dark section banner: 9 pt label in a 0.60 cm bar, gold rules, section dots.
- A 15 pt frame title in a 4.4 ex purple bar; the title and the 3.2 ex logo are vertically centred.
- A 9 pt footer in a 5.2 ex bar; the background covers the text, the date is padded from the colour edge, and the original purple/gold/cream colours are kept.
- `lmodern` is loaded for scalable Latin fonts; box-badness settings live in the theme.

The poster and article-report modes are unchanged.

## Article Report Mode

The template now supports an **article report mode** that is particularly useful for group meetings and academic presentations where you need to report on a specific article or paper.

### Features
- Use a figure or image instead of the title on the title page
- Automatically adds "Reporter:" in front of the author name
- Maintains all other presentation features while optimizing for article reporting

### Usage
To enable article report mode, add the `articlereport` option when loading the theme:

```latex
\usetheme[presentation,articlereport]{nju}
```

Then set the article information using the `\articleinfo` command:

```latex
\articleinfo{\includegraphics[height=0.4\textheight]{images/your-article-image.png}}
```

## Citations (v0.3.0)

The examples use `natbib` author-year citations with the ICLR 2027 setup:

```latex
\usepackage{nju-cite}
...
Following \citet{he2016deep}, the residual connection is ...
\citep{vaswani2017attention} introduces self-attention.
```

- `\citet{key}` prints the author-year citation in gold and automatically adds a
  brief footnote on the same page (first author, year, title, venue).
- `\citep{key}` prints the parenthetical author-year citation.
- `nju-cite.sty` uses `\setcitestyle{authoryear,round,citesep={;},aysep={,},yysep={;}}`
  and makes `\citet`/`\citep` robust under beamer, so no `\protect` is needed.
- The footnote text is generated from the `.bib` file by:

  ```bash
  python3 make_shortrefs.py ref.bib
  ```

  The generated `shortrefs.tex` is read automatically. An unknown key falls back
  to the plain author-year citation.
- `iclr2027_conference.bst` provides the reference formatting: full author lists,
  blue paper titles, gold venue names, and the usual URL style.

Build an example with:

```bash
python3 make_shortrefs.py ref.bib
latexmk -xelatex presentation.tex
```

## Examples
- `presentation.tex`: Example of a presentation using the NJU theme.
- `poster.tex`: Example of a poster using the NJU theme.
- `articlereport.tex`: Example of an article report using the NJU theme.

The compiled PDF files can be found in `images/poster.pdf` and `images/presentation.pdf`.
