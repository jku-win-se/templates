# JKU WIN-SE LaTeX Templates

LaTeX templates for student and doctoral work at the **Institute of Business Informatics – Software Engineering (WIN-SE)**, Johannes Kepler University Linz. Each template includes the official JKU cover sheet, sensible defaults for layout and bibliography, and example content you can overwrite.

| Folder | Use it for |
|---|---|
| [`bac_master_phd/`](bac_master_phd) | Bachelor's, master's, and phd theses  |
| [`phd_expose/`](phd_expose) | PhD exposé / research proposal |
| [`seminar/`](seminar) | Seminar papers (e.g. *Seminar aus Software Engineering*) |

`bac_master_phd.zip` contains the thesis template, ready to upload to Overleaf.

## Getting started

### Overleaf
1. Download `bac_master_phd.zip` (or zip the template folder you need).
2. In Overleaf: **New Project → Upload Project** and select the zip.
3. Make sure `main.tex` is set as the main document.


> **Seminar template:** it uses the `svg` package, which calls Inkscape to convert SVG figures. Install Inkscape and compile with `--shell-escape` (e.g. `latexmk -pdf -shell-escape main.tex`). On Overleaf this works out of the box. If you don't use SVG figures, you can remove `\usepackage{svg}` from `imports.sty`.

## Configuring a template

All settings you need to change are at the top of `main.tex`, marked with `CONFIG` comments. Don't edit `coversheet.tex` unless you know what you're doing.

### Thesis (`bac_master_phd/main.tex`)

| Setting | What to set |
|---|---|
| **Language** | `\engtrue` for English, `\engfalse` for German. Controls babel, the cover sheet and the front-matter headings. |
| **Thesis type** | `\def\type{…}` — `0` dissertation, `1` diploma thesis, `2` master's thesis, `3` bachelor's thesis. |
| **Degree** | `\def\degree{…}` — exactly as stated in your curriculum, e.g. `Bachelor of Science`, `Master of Science`, `Doktor der Sozialwissenschaften`. |
| **Cover sheet** | `\thtitle`, `\name`, `\supervisor`, `\secondexaminer` (dissertations only), `\assist` (co-supervisor), `\submitted` (month and year), `\study`, `\institute`. |
| **Supervisor salutation** | For the German cover sheet, set `\supvismaletrue` / `\supvismalefalse` (and `\secexmale…` for the second examiner) in `coversheet.tex`. |

Content files:
- `acknowledgements.tex`, `kurzfassung.tex` (German abstract), `abstract.tex` – front matter
- `intro.tex`, `examples.tex` – chapters; add your own and `\input` them in `main.tex`
- `eidesstattliche.tex` – sworn statement (mandatory, last page)
- `references.bib` – bibliography


## Useful macros

Available in all templates for consistent cross-referencing (label your elements with the matching prefix):

| Macro | Output | Label prefix |
|---|---|---|
| `\citechap{x}` | Chapter 1 | `chap:` (thesis/exposé only) |
| `\citesec{x}` | Section 1.2 | `sec:` |
| `\citefig{x}` | Fig. 3 | `fig:` |
| `\citetable{x}` | Table 2 | `tab:` |
| `\citelisting{x}` | Listing 1 | `lst:` |
| `\citealgo{x}` | Listing 1 | `algo:` |

For drafting: `\note{…}` (purple) and `\commnt{…}` (green) highlight text, and `\todo{…}` from `todonotes` adds margin notes. Remove them before submission.

The example files (`examples.tex`) show figures, tables, subfigures and citations.

## Bibliography

References go in `references.bib` and are processed with BibTeX. The default style is `alpha`; `abbrv` and `apalike` are included as commented-out alternatives at the end of `main.tex`.

## Credits

- Thesis and seminar templates: Michael Vierhauser, Institute of Business Informatics – Software Engineering (2019)
- JKU cover sheet: Andreas Neubauer (2016)
- Maintained by the [JKU WIN-SE group](https://github.com/jku-win-se). Found a problem or have an improvement? Open an issue or a pull request.
