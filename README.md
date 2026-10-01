# CV: Muhammad Arya Fikriansyah

LaTeX source for my resume. The compiled PDF is not kept in this repository.

## Layout

```
resume.tex            preamble, fonts, and section order
custom-commands.tex   macros for headings, entries, and bullet lists
src/
  heading.tex         name and contact line
  summary.tex
  experience.tex
  skills.tex
  education.tex
  publications.tex
  honors.tex
  projects.tex        not included in the build
  licenses.tex        not included in the build
```

Each section is one file. To add, remove, or reorder a section, edit the `\input` lines in `resume.tex`.

## Build

The preamble uses `\pdfgentounicode` and `glyphtounicode`, so compile with pdfLaTeX.

**Overleaf:** upload the repository, keep `resume.tex` as the main document, and leave the compiler on pdfLaTeX.

**Local:** with a TeX distribution installed, run:

```bash
pdflatex resume.tex
```

Packages used: `lato`, `fontenc`, `microtype`, `fontawesome5`, `titlesec`, `enumitem`, `hyperref`, `fancyhdr`, `tabularx`, `ragged2e`, `babel`, `fullpage`, `marvosym`, `latexsym`, `color`, `verbatim`.

## Text layer

Applicant tracking systems read the text inside the PDF, not the rendered page. Three settings in `resume.tex` keep that text plain:

- `\DisableLigatures` stops "fi", "fl", and "ff" from becoming single glyphs. With ligatures on, the email address and profile URLs were extracted with a ligature character in place of "fi".
- T1 font encoding makes accented letters such as "ï" extract as one character.
- Hyphenation is off, so a keyword is never split across two lines.

The contact line is plain text, without icon fonts.

To check a build, extract the text and read it:

```bash
pdftotext -enc UTF-8 resume.pdf -
```

The email, URLs, and section order should come out exactly as written in the source.

## Credits

The template is by Audric Serador, based on [sb2nov/resume](https://github.com/sb2nov/resume). The template header in `resume.tex` lists the MIT license.
