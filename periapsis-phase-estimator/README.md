# Periapsis-Shift Extraction: Accumulated-Phase Estimator

**Author:** Uppala Sri Sai Vithesh  
**Affiliation:** Independent Student Researcher, Andhra Pradesh, India  
**Contact:** srisaivitheshuppala99@gmail.com  
**Manuscript date:** 22 November 2026

## Overview

This repository contains the LaTeX source and a compiled PDF of the manuscript:

> *Conditioning of periapsis-shift extraction from orbit integrations: an accumulated-phase estimator and its error scaling.*

The study examines a phase-based estimator for extracting relativistic periapsis shifts from numerical orbit integrations in Schwarzschild spacetime, and compares it with event-based extraction under the numerical protocols described in the manuscript.

The manuscript explicitly does **not** claim to introduce new gravitational physics.

## Repository contents

- `manuscript/Periapsis_Phase_Estimator_Manuscript.pdf` — compiled 15-page manuscript.
- `manuscript/latex-source/main.tex` — main LaTeX source.
- `manuscript/latex-source/numbers.tex` — numerical macros used by the manuscript.
- `manuscript/latex-source/tab_*.tex` — manuscript tables.
- `manuscript/latex-source/figures/` — six PDF figures included in the manuscript.

## Build the manuscript

A LaTeX installation with the packages used in `main.tex` is required. From the source directory:

```bash
cd manuscript/latex-source
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

The supplied source was compiled successfully with `latexmk -pdf`; the resulting PDF was 15 pages.

## Reproducibility materials: important scope note

**This repository was assembled from the arXiv source ZIP supplied for this upload.** That ZIP contains the manuscript source, table fragments, numerical macros and six figure PDFs. It does not contain the Python research implementation, raw numerical datasets, test suite, or figure-generation scripts.

Accordingly, this repository is a **manuscript/source repository, not a complete computational reproducibility archive**. The manuscript's statements about code and data availability should be accompanied by a separate public code-and-data repository or archive before treating the project as fully reproducible. Do not infer or fabricate missing code or datasets from the manuscript.

## Publication status

This repository does not assert that the manuscript has been accepted by a journal, peer-reviewed, or assigned an arXiv identifier. Update this section only when those events have actually occurred.

## Licensing

The manuscript's arXiv distribution licence and any licence for source code or data are separate matters. No new blanket licence is assigned by this repository package. Before making the GitHub repository public, choose and add a licence only after confirming that you have the rights to license each included component. Do not apply an MIT licence to the manuscript merely because you intend to use MIT for software.

## Contact

For scientific comments, corrections, or questions, contact the author at the address above.
