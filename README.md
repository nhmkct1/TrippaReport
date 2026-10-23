# Trippa Project Report

[![Build report PDF](https://github.com/nhmkct1/TrippaReport/actions/workflows/build-report.yml/badge.svg)](https://github.com/nhmkct1/TrippaReport/actions/workflows/build-report.yml)

English LaTeX report covering three chapters: Introduction, Existing System Analysis, and System Analysis. Content is based on the corresponding pages under **DACN Report** in Confluence. This report documents project requirements and intentions; it does not claim that the requirements have been implemented or measured.

## Build on Windows

Install a current **MiKTeX** or **TeX Live** distribution with XeLaTeX, the TeX Gyre fonts, and latexmk. MiKTeX also needs **Perl** to run latexmk; Strawberry Perl or Git for Windows' bundled Perl can provide it. Restart the terminal after installation so the tools are on `PATH`. In MiKTeX Console, enable installation of missing packages, or install the packages used by `report.tex` in advance.

From the repository root in PowerShell:

```powershell
latexmk report.tex
```

`latexmkrc` selects XeLaTeX and writes output to **`build/report.pdf`**. It automatically repeats compilation to resolve the contents, table list, and cross-references. No Overleaf account or bibliography processor is required.

If MiKTeX cannot find Perl and Git for Windows is installed in its default location, add its bundled Perl for the current terminal session:

```powershell
$env:PATH = 'C:\Program Files\Git\usr\bin;' + $env:PATH
latexmk report.tex
```

When diagnosing a failure, check `build/report.log`. To force a complete rebuild:

```powershell
latexmk -gg report.tex
```

Linux/TeX Live dependencies used by CI: `latexmk`, `texlive-xetex`, `texlive-latex-extra`, `texlive-fonts-recommended`, and `fonts-texgyre`. Build with the same `latexmk report.tex` command.

## Download the GitHub-built PDF

1. Open [Build report PDF](https://github.com/nhmkct1/TrippaReport/actions/workflows/build-report.yml).
2. Select the successful run for the desired commit.
3. Download the `trippa-report-<commit SHA>` artifact under **Artifacts**, or use the link in the run summary.
4. Extract `report.pdf`. The archive also contains `source-commit.txt` and `report.sha256` so the PDF can be matched to its source revision.

GitHub may require sign-in to download artifacts. Artifacts are retained for 30 days, subject to repository policy. Use **Run workflow** to generate a fresh artifact when needed. Every push and pull request also triggers a build. The workflow fails on compilation errors, overflowing boxes, missing glyphs, or unresolved/multiply defined references. Build logs are uploaded on failure when available.

## Edit the report

- `report.tex`: document layout, typography, contents, and chapter inclusion.
- `metadata.tex`: temporary title, institution, authors, supervisor, and date; replace when the official cover is supplied.
- `chapters/`: editable chapter sources. Chapter and section numbers are generated automatically.
- `images/`, `diagrams/`: reserved for approved assets; no diagrams have been invented.
- `refs/source-notes.md`: provenance, conversion decisions, and outstanding content questions.
- `.github/workflows/build-report.yml`: automatic PDF build and artifact upload.

Keep chapter content in the chapter files. Long tables repeat their column headers across page breaks. The five-column system comparison uses a landscape page. FR/NFR identifiers and unresolved TBD entries are retained from Confluence. The markers **[source TBD]** identify incomplete source references that require confirmation; they are not fabricated bibliography entries.

Generated PDFs and build files are ignored by Git. Commit the source files, then push to obtain a downloadable PDF artifact.
