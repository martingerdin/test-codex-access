---
title: New project template
status: active      # Options: active, waiting, paused, finished, cancelled, archived
category: research  # Options: research, clinical, education, personal
---

<!-- TEMPLATE-ONLY: remove everything above the PROJECT README marker after initialization. -->
# Using this template

A minimal template for research and clinical quality-improvement projects, based on [Good Enough Practices in Scientific Computing](https://carpentries-lab.github.io/good-enough-practices/index.html).

1. Copy the template into a named project folder.
2. Replace the examples below with project details and setup instructions. Keep only guidance that applies.
3. Update `CITATION` and the copyright placeholders in `LICENSE`. Check that the rights holders agree to the licenses and that institutional, funder, and publication rules allow them. Record exceptions there.
4. Remove this template section, the boundary marker below, and the setup note in `LICENSE`.

<!-- PROJECT README: keep and adapt everything below. Remove this marker after initialization. -->
# Name <!-- Replace with the project name. -->

> Example: Improving discharge follow-up

## Description

<!-- Short description of the project and its aim. -->

> Example: Evaluate whether a discharge checklist improves follow-up within seven days for patients leaving the medical ward.

## Team and contact

<!-- Names, roles, and contact person. -->

> Example: Alex Smith (clinical lead) and Sam Lee (analyst). Contact: alex.smith@example.org.

## Data and approvals

<!-- Sources, approved access/storage, and relevant permissions. No sensitive information or credentials. -->

> Example: Encounter and follow-up records are stored in approved institutional storage. Access is restricted to authorized team members. Ethics and data-access decisions are recorded in `doc/approvals/`. Patient-level data are kept out of version control.

## Setup and workflow

<!-- Specify required software/packages, environment setup, and commands to run the analysis and render manuscripts. -->

> Example: Install R, Quarto, and the dependencies listed in `src/DESCRIPTION`. Once the project scripts and manuscript exist, run `Rscript src/run_analysis.R`, then `quarto render doc/manuscripts/report.qmd`.

## Project layout

| Location | Contents |
| --- | --- |
| `data/` | Non-sensitive metadata: data dictionaries, code lists, and schemas. |
| `doc/notebook.md` | Dated decisions, methods, and analysis notes. |
| `doc/project-planning/` | Concept notes and proposals. |
| `doc/approvals/` | Ethics, consent, data-access, and other permissions. |
| `doc/protocols/` | Protocols, analysis plans, and procedures. |
| `doc/manuscripts/` | Manuscript drafts and submission materials. |
| `results/` | Generated data, tables, and figures that are safe to store here. |
| `src/` | Data-access, cleaning, and analysis code. |
| `CITATION`, `LICENSE` | Citation instructions and reuse terms. |

Use document subfolders only when needed. Small projects can keep documents directly in `doc/`. Keep folder guidance in this README rather than separate folder READMEs.

## Reusable R functions

For functions shared across analyses or Quarto manuscripts, use a local R package in `src/`: metadata and dependencies in `src/DESCRIPTION`, functions in `src/R/`. Give the package a unique project-specific name. It need not be called `src` or published to CRAN.

From the repository root, load functions during development:

```r
pkgload::load_all("src")
```

In a Quarto setup chunk, use `pkgload::load_all("../../src")` for a document in `doc/manuscripts/` with Quarto’s default document-relative working directory. If Quarto is configured to execute from the project root, use `"src"` instead.

For installed use, run `devtools::install("src")`, then `library(yourPackageName)`. Add tests in `src/tests/testthat/` as needed. For a few one-off helpers, use `source()` with the path to the file.

## Working practices

- Keep raw data unchanged in approved storage. Record where the data came from, how to access them, and how they were changed.
- Never commit sensitive data or credentials. Avoid committing large or easily regenerated outputs.
- Use descriptive filenames and `YYYY-MM-DD` dates. Make analyses scriptable and test important steps.
- Track changes in version control and back up through approved locations.

## Licensing

See [`LICENSE`](LICENSE) for the terms. MIT applies to code and project documentation. CC BY 4.0 applies to manuscript/publication prose and original figures, excluding executable code. Datasets are excluded. Third-party terms remain unchanged. Record exceptions and approved data-sharing terms there, and identify publication figures stored in `results/` if they should use CC BY. An open license does not give permission to share sensitive data.
