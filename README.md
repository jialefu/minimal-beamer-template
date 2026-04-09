# Minimal Beamer Template

![License: MIT](https://img.shields.io/badge/License-MIT-2ea44f.svg)
![Engine: XeLaTeX](https://img.shields.io/badge/Engine-XeLaTeX-0A7EA4.svg)
![Format: Beamer](https://img.shields.io/badge/Format-Beamer-1f6feb.svg)
![Languages: EN+ZH](https://img.shields.io/badge/Languages-English%20%2B%20Chinese-238636.svg)

A minimal, reusable Beamer template with separate English and Chinese demo decks powered by one shared style package.

## Why This Project

This repository is designed for people who want slides that feel clean, academic, and easy to adapt without inheriting a sprawling theme codebase.

- One shared style package instead of a scattered initialization folder
- Separate English and Chinese entry files on the same branch
- Fast institutional rebranding through logo, metadata, and color overrides
- Standard Beamer authoring flow for figures, tables, equations, citations, and code blocks

## Highlights

| Area | What you get |
| --- | --- |
| Language support | `main-en.tex` for English and `main-zh.tex` for Chinese |
| Style architecture | One reusable package: `minimalistslides.sty` |
| Rebranding | Replace the logo and adjust colors without rewriting the layout |
| Authoring | Familiar Beamer patterns instead of a heavy custom abstraction layer |
| Build workflow | `latexmk -xelatex main-en.tex` or `latexmk -xelatex main-zh.tex` |

## Preview

<p align="center">
  <img src="imgs/main_page-0001.jpg" width="45%" alt="Cover slide preview">
  <img src="imgs/main_page-0004.jpg" width="45%" alt="Section divider preview">
</p>

<p align="center">
  <img src="imgs/main_page-0011.jpg" width="45%" alt="Block styling preview">
  <img src="imgs/main_page-0014.jpg" width="45%" alt="Reference slide preview">
</p>

## Repository Structure

```text
.
|-- figs/                   # Logo and demo image assets
|-- imgs/                   # Preview images for the repository page
|-- minimalistslides.sty    # Shared package for theme, layout, listings, and commands
|-- main-en.tex             # English demo deck
|-- main-zh.tex             # Chinese demo deck
|-- reference.bib           # Bibliography examples
`-- .latexmkrc              # Recommended latexmk build configuration
```

## Quick Start

### Build the English version

```bash
latexmk -xelatex main-en.tex
```

### Build the Chinese version

```bash
latexmk -xelatex main-zh.tex
```

Manual fallback:

```bash
xelatex main-en.tex
bibtex main-en
xelatex main-en.tex
xelatex main-en.tex
```

```bash
xelatex main-zh.tex
bibtex main-zh
xelatex main-zh.tex
xelatex main-zh.tex
```

## Customization

Edit the metadata block near the top of either entry file:

```latex
\renewcommand{\presentationtitle}{Minimalist Academic Slides}
\renewcommand{\presentationauthor}{Zhang San}
\renewcommand{\presentationadvisor}{Li Si}
\renewcommand{\presentationinstitution}{\themename}
\renewcommand{\presentationdate}{\today}
```

Typical theme-level changes:

```latex
\setthemename{Your Institution}
\setthemelogo{figs/logo.jpg}
\setthemeprimaryrgb{48}{95}{33}
\setthemeaccentrgb{95}{33}{48}
```

## Usage Notes

### Section divider

```latex
\section{Method}
\subsection{Training Pipeline}
\makesection
```

### Standard content slide

```latex
\begin{frame}{Method}{Training Pipeline}
    \begin{block}{Overview}
        Your content goes here.
    \end{block}
\end{frame}
```

### Plain cover or closing slide

```latex
\begin{frame}[plain]
    % Custom title or closing page
\end{frame}
```

## Design Change

Earlier versions split Chinese and English across different Git branches and stored theme logic under `init/`. This repository now keeps both languages on the same branch and consolidates the theme into a single package file, which makes the project easier to understand, reuse, and maintain.

## Topics

Suggested GitHub topics:

`latex` `beamer` `slides` `presentation-template` `academic-template` `thesis-defense` `xelatex` `beamer-theme` `ctex`

## License

This project is released under the MIT License. See `LICENSE` for details.
