# USTHB Thesis Template - Multilingual XeTeX/LuaTeX Template

A complete, production-ready LaTeX thesis template with native support for **English**, **French**, and **Arabic** languages using `polyglossia` and `fontspec`.

## Project Structure

```plaintext
main.tex                    - Main document (compiles all components)
titlepage.tex              - Separate title page with customizable order number
references.bib             - Bibliography database (BibTeX format)
chapters/
  ├── _Introduction.tex    - Introduction chapter
  ├── chapter1.tex         - Main content chapter 1
  ├── chapter2.tex         - Main content chapter 2
  ├── chapter3.tex         - Main content chapter 3
  └── Conclusion.tex       - Conclusion chapter
abstracts/
  ├── abstract_en.tex      - English abstract
  ├── abstract_fr.tex      - French abstract (Résumé)
  └── abstract_ar.tex      - Arabic abstract (الملخص)
img/                        - Image directory for figures
Thanks.tex                  - Acknowledgments page
```

## Language Support

Full support for three languages with automatic script switching:

- **French** (main language)
- **English** (secondary)
- **Arabic** (with RTL support via Segoe UI font)

### Usage Examples

Switch languages anywhere in your document:

```latex
\selectlanguage{french}
Ceci est un texte en français.

\selectlanguage{english}
This is English text.

\selectlanguage{arabic}
\arabicfont
هذا نص باللغة العربية
```

For Arabic sections, always include `\arabicfont` to render characters correctly:

```latex
\selectlanguage{arabic}
\arabicfont
نصك العربي هنا
```

## Key Features

✅ **Separate Title Page** — Customizable with title, author, date, and order number  
✅ **Modular Chapters** — Each chapter in its own `.tex` file for easy management  
✅ **Multi-language Abstracts** — Three abstract files (English, French, Arabic)  
✅ **Bibliography Support** — Using `natbib` with standard BibTeX (`plainnat` style)  
✅ **Professional Formatting** — Custom chapter styling, page layout, and document structure  
✅ **Acknowledgments Page** — `Thanks.tex` for dedications and thanks  
✅ **Comprehensive TOC** — Table of contents, list of figures, list of tables, list of algorithms  

## Document Information

Customize in `main.tex` (lines 42-45):

```latex
\title{Your Thesis Title}
\author{Your Name}
\newcommand{\ordernumber}{N/A}    % Order/registration number
\date{\today}
```

## Compiling the Document

**Required**: XeTeX or LuaTeX (for polyglossia and fontspec support)

### Basic compilation

```bash
xelatex main.tex
```

### Complete compilation (with bibliography)

```bash
xelatex main.tex
bibtex main
xelatex main.tex
xelatex main.tex
```

### Using a build tool (latexmk)

```bash
latexmk -xelatex -interaction=nonstopmode main.tex
```

**Note**: Do NOT use `pdflatex` — it's incompatible with `polyglossia` and `fontspec`.

## Fonts

### Main Font: Fira Sans

- Used for English and French text
- Professional, modern sans-serif font
- Install from: <https://fonts.google.com/specimen/Fira+Sans>

### Arabic Font: Segoe UI

- Built-in Windows font with Arabic script support
- Alternative fonts: Amiri, DejaVu Sans, Simplified Arabic

To change fonts, edit `main.tex`:

```latex
\setmainfont{Your Font Name}
\newfontfamily\arabicfont[Script=Arabic]{Your Arabic Font}
```

## Customization Guide

### 1. Edit Title Page

Modify `titlepage.tex` to customize layout, colors, and design.

### 2. Add Chapters

1. Create a new file `chapters/chapterN.tex`
2. Add to `main.tex`:

   ```latex
   \input{chapters/chapterN.tex}
   ```

### 3. Manage Bibliography

- Add references to `references.bib` in BibTeX format
- Cite in text: `\cite{key}` or `\citet{key}`
- Add at end of `main.tex`:

   ```latex
   \bibliography{references}
   ```

### 4. Add Figures

Place images in `img/` directory and reference:

```latex
\includegraphics[width=0.8\textwidth]{img/your-image.png}
```

### 5. Switch Arabic Font

Edit the Arabic font family in `main.tex`:

```latex
\newfontfamily\arabicfont[Script=Arabic]{Amiri}
```

## Math Environments

Pre-defined theorem-like environments (in French):

- `\begin{theorem}` — Théorème
- `\begin{lemme}` — Lemme
- `\begin{proposition}` — Proposition
- `\begin{definition}` — Définition
- `\begin{example}` — Exemple
- `\begin{remark}` — Remarque

Example:

```latex
\begin{theorem}
Your theorem statement here.
\end{theorem}
```

## Page Layout

- **Paper size**: A4 (210 × 297 mm)
- **Font size**: 12pt
- **Line spacing**: 1.5 (one-and-a-half)
- **Margins**: Top 2.5cm, Bottom 3cm, Left 2.5cm, Right 2cm
- **Paragraph style**: Justified

## Troubleshooting

### Missing Arabic characters

- Ensure using `xelatex` (not `pdflatex`)
- Add `\arabicfont` before Arabic text
- Install Segoe UI or alternative Arabic font

### Font not found error

- Install required fonts on your system
- Update font names in `main.tex`

### Bibliography not showing

- Run: `bibtex main` before final `xelatex` compilation
- Check `references.bib` format

## Document Components

| File | Purpose |
| ------ | --------- |
| `main.tex` | Executive document file—compile this |
| `titlepage.tex` | Title page with customizable fields |
| `Thanks.tex` | Acknowledgments page |
| `chapters/*.tex` | Main content chapters |
| `abstracts/*.tex` | Three-language abstracts |
| `references.bib` | Bibliography database |

## Version Information

- **XeTeX/LuaTeX compatible**: Yes
- **polyglossia**: v1.46+
- **fontspec**: v2.8+
- **natbib**: v8.31+

## License & Credits

USTHB Thesis Template — Multilingual Edition
Based on USTHB (Université des Sciences et de la Technologie Houari Boumediène) standards
