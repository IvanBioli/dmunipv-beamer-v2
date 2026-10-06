# dmpavia-slide

Beamer theme for the Mathematics Department of the University of Pavia,
restyled in 2026 to match the DM UniPV PowerPoint template (v4).

Compiles with pdfLaTeX (uses the `caladea` and `carlito` packages) or with
XeLaTeX / LuaLaTeX (uses the system fonts Caladea and Carlito via fontspec).
See `template.tex` for a full demo.

## Setup

```latex
\documentclass{beamer}
\usetheme[sectionstyle=diagonal]{dmpavia}   % or sectionstyle=numeral | none
\title{...} \subtitle{...} \author{...} \date{...}
\course{Department of Mathematics · University of Pavia}   % label above the title
```

## Slides

| What | How |
|---|---|
| Title slide | `\maketitle` |
| Outline (maroon panel, numbered sections) | `\outlineframe` or `\outlineframe[Agenda]` |
| Section header | automatic at each `\section`; style set once by the theme option. `\sectionlead{...}` before `\section` adds a one-line summary |
| Kicker above the frame title | defaults to the section name; `\framekicker{...}` or `\nokicker` inside a frame |
| Column headings | `\colheading{Kept from Beamer}` |
| Big numbers | `\bignumber{16}{slide layouts}` (use inside columns) |
| Photo left, maroon panel right | `\begin{picsplit}[kicker]{image}{title} ... \end{picsplit}` |
| Photo on the right edge | `\begin{sidepic}{image}{title} ... \end{sidepic}` |
| Quote on warm grey | `\quoteframe{statement}{attribution}` |
| Key message on maroon | `\keymessage{message}{source}` |
| Closing slide | `\backmatter` |

Pictures are cropped to fill their area, whatever their aspect ratio.

## Cards (boxes)

```latex
\begin{card}[<styles>]{Label} ... \end{card}
\begin{definitionbox}{Definition} ... \end{definitionbox}   % grey
\begin{theorembox}{Theorem (Rademacher)} ... \end{theorembox} % maroon tint
\begin{resultbox}{Theorem (Banach)} ... \end{resultbox}     % tint, larger text
\begin{takeaway} ... \end{takeaway}                          % maroon, "Key takeaway"
```

Styles combine freely: `grey`, `tint`, `maroon`, `outline`, `accent=<colour>`,
`large`, `serif`, `sans`, plus any tcolorbox option (`width=`, `height=`,
`equal height group=<name>` to align cards in columns, ...).

Beamer's own `theorem`, `lemma`, `corollary` (tint), `definition` (grey),
`example` (green), `block` (grey), `alertblock` (tint) and `exampleblock`
are drawn as cards automatically. `colorblock` from the 2025 theme still works.

## Closing slide

```latex
\closingcontact{\href{mailto:name@unipv.it}{name@unipv.it}}
\paperqr{https://arxiv.org/abs/XXXX.XXXXX}   % large QR, optional label: \paperqr[Preprint]{...}
\githubqr{...} \linkedinqr{...} \webpageqr{...} \addqr{Label}{url}
\closingtitle{Thank you} \closingmessage{Questions and comments are welcome}
```

QR codes are generated from the URLs at compile time (package `qrcode`).

## Backward compatibility

`\course`, `\IDnumber`, `\titlebackground*`, `\footlinepayoff`, `\themecolor{main}`,
`chapter`, `sidepic`, `colorblock`, `\backmatter` and `\thankyoublock` still work.
`\footlinecolor` is accepted but no longer changes the footline.

## License and Credits: GPL3

This template is based on [SINTEF Presentation](https://www.overleaf.com/latex/templates/sintef-presentation/jhbhdffczpnx) from [Federico Zenith](mailto:federico.zenith@sintef.no) and its derivation [Beamer-LaTeX-Themes](https://github.com/TOB-KNPOB/Beamer-LaTeX-Themes) from Liu Qilong and Andrea Gasparini, [Mattia Ippoliti](https://github.com/MattiaIppoliti) and [Fabio Durastante](https://fdurastante.github.io/).

In compliance with the license with which it was obtained, the modifications are
released and made available under the [GNU GPL3](https://www.gnu.org/licenses/gpl-3.0.en.html).
