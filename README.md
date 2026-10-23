# Trippa Project Report

[![Build report PDF](https://github.com/nhmkct1/TrippaReport/actions/workflows/build-report.yml/badge.svg)](https://github.com/nhmkct1/TrippaReport/actions/workflows/build-report.yml)

English LaTeX report covering three chapters: **Introduction**, **Functional and Non-Functional Requirements**, and **Architecture Design**. Introduction and all 173 FR/NFR identifiers are retained from **DACN Report** in Confluence. The architecture chapter is a new proposed design: four alternatives are compared, and a modular monolith with layered modules is selected. It includes a decision matrix, runtime/dependency diagrams, ownership rules, principal flows, trade-offs and references.

The current revision is a **draft for review**, published with the user's approval. Cover fields that have not been supplied remain TBD. It describes intended requirements and proposed design decisions, not verified implementation or measured performance. Existing-system comparisons, stakeholders, business-rule exposition, prioritization and the old traceability section are excluded from this revision. Requirements that mention those subjects remain intact. Use Case Table, Use Case Diagram, Activity Diagram, Sequence Diagram and Class Diagram are retained as explicit TBD subsections under System Models, following the Confluence checklist.

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
- `frontmatter/cover.tex`: English cover adapted from the supplied HCMUT template, including its double frame.
- `metadata.tex`: cover text and pending committee, supervisor, program, students/IDs and defense date.
- `chapters/`: editable chapter sources. Chapter and section numbers are generated automatically.
- `diagrams/`: editable TikZ sources for the proposed runtime structure and module layers; compiled directly by LaTeX.
- `images/hcmut.png`: university logo supplied by the user, included without altering the original image.
- `refs/source-notes.md`: provenance, conversion decisions, and outstanding content questions.
- `.github/workflows/build-report.yml`: automatic PDF build and artifact upload.

Keep chapter content in the chapter files. Long tables repeat their column headers across page breaks. All 111 functional and 62 non-functional requirement identifiers and all 13 requirement TBD occurrences are retained from Confluence. Architecture references are listed inside Chapter 3, so the report has exactly three numbered chapters. No programming language, framework, cloud provider or separate AI service is imposed by the design.

Generated PDFs and build files are ignored by Git. Commit the source files, then push to obtain a downloadable PDF artifact.
