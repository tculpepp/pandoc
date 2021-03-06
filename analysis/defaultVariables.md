## Metadata

- Title
- Author
- Date
- subtitle
- abstract
- keywords
- subject
- description
- category

## Language

- lang - Identifies the main language
- dir - base script directory
  
## LaTeX

- Layout
  - BLock headings, "make \paragraph and \subparagraph (fourth- and fifth-level headings, or fifth- and sixth-level with book classes) free-standing rather than run-in; requires further formatting to distinguish from \subsubsection (third- or fourth-level headings). Instead of using this option, KOMA-Script can adjust headings more extensively:"
  - classoption, "option for document class, e.g. oneside; repeat for multiple options:"
  - documentclass, "document class: usually one of the standard classes, article, book, and report; the KOMA-Script equivalents, scrartcl, scrbook, and scrreprt, which default to smaller margins; or memoir
  - geometry. "option for geometry package, e.g. margin=1in; repeat for multiple options:"
  - hyperrefoptions, "option for hyperref package, e.g. linktoc=all; repeat for multiple options:"
  - indent, "if true, pandoc will use document class settings for indentation (the default LaTeX template otherwise removes indentation and adds space between paragraphs)"
  - linestretch, "adjusts line spacing using the setspace package, e.g. 1.25, 1.5"
  - margin-left etc., "sets margins if geometry is not used (otherwise geometry overrides these)"
  - pagestyle, "control \pagestyle{}: the default article class supports plain (default), empty (no running heads or page numbers), and headings (section titles in running heads)"
  - papersize, "paper size, e.g. letter, a4"
  - secnumdepth, "numbering depth for sections (with --number-sections option or numbersections variable)"
- Fonts
  - fontenc, "allows font encoding to be specified through fontenc package (with pdflatex); default is T1 (see LaTeX font encodings guide)"
  - fontfamily, "font package for use with pdflatex: TeX Live includes many options, documented in the LaTeX Font Catalogue. The default is Latin Modern."
  - fontfamilyoptions, "options for package used as fontfamily; repeat for multiple options. For example, to use the Libertine font with proportional lowercase (old-style) figures through the libertinus package:"
  - fontsize, "font size for body text. The standard classes allow 10pt, 11pt, and 12pt. To use another size, set documentclass to one of the KOMA-Script classes, such as scrartcl or scrbook."
  - mainfont / sansfont / monofont / mathfont / CJKmainfont, "font families for use with xelatex or lualatex: take the name of any system font, using the fontspec package. CJKmainfont uses the xecjk package."
  - mainfontoptions / sansfontoptions / monofontoptions / mathfontoptions / CJKoptions, "options to use with mainfont, sansfont, monofont, mathfont, CJKmainfont in xelatex and lualatex. Allow for any choices available through fontspec; repeat for multiple options. For example, to use the TeX Gyre version of Palatino with lowercase figures:"
  - microtypeoptions, "options to pass to the microtype package"
- Links
  - colorlinks, add color to link text; automatically enabled if any of linkcolor, filecolor, citecolor, urlcolor, or toccolor are set
  - linkcolor / filecolor / citecolor / urlcolor / toccolor, "color for internal links, external links, citation links, linked URLs, and links in table of contents, respectively: uses options allowed by xcolor, including the dvipsnames, svgnames, and x11names lists"
  - links-as-notes, "causes links to be printed as footnotes"
- Front matter
  - lof / lot, "include list of figures, list of tables"
  - thanks, "contents of acknowledgments footnote after document title"
  - toc, "include table of contents (can also be set using --toc/--table-of-contents)"
  - toc-depth, "level of section to include in table of contents"
- BibLaTeX Bibliographies, "These variables function when using BibLaTeX for citation rendering."
  - biblatexoptions, "list of options for biblatex"
  - biblio-style, "bibliography style, when used with --natbib and --biblatex."
  - biblio-title, "bibliography title, when used with --natbib and --biblatex."
  - bibliography, bibliography to use for resolving references
  - natbiboptions, list of options for natbib
