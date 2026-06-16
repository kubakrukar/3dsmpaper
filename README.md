# 3D sketch maps paper

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20187706.svg)](https://doi.org/10.5281/zenodo.20187706)

Code, data, and sketch-map gallery for:

> Krukar, J., Aly, A., Baecker, L., Heming, L. M., Zhao, J., & Schwering, A. (2026). 3D environments require 3D visualisations: The limitations of 2D sketch maps in capturing spatial knowledge. *International Journal of Geographical Information Science*, 1–33. https://doi.org/10.1080/13658816.2026.2684650

A browsable landing page with a side-by-side viewer for every 2D / 3D sketch is published at: **https://kubakrukar.github.io/3dsmpaper/**

## Overview

This repository contains all data, code, and materials necessary to reproduce all findings reported in the manuscript. All file paths are relative, and the analysis can be reproduced by following the step-by-step instructions below.

Code and text are integrated: in order to reproduce any figure or result from the manuscript, locate the relevant code chunk in `manuscript.Rmd`.

## Repository layout

```
.
├── manuscript.Rmd         # main manuscript (knit -> manuscript.pdf)
├── Appendix.Rmd           # supplementary materials
├── manuscript.pdf         # rendered manuscript
├── clean_data/            # processed data used by the analysis
├── raw_data/
│   ├── exp1/sketchmaps/2D # 2D pen-and-paper sketches (.jpg)
│   ├── exp1/sketchmaps/3D # 3D Gravity Sketch exports (.fbx, .zip)
│   ├── exp2/sketchmaps/2D
│   └── exp2/sketchmaps/3D
├── models/                # cached brms model fits (.rds, gitignored)
├── index.html             # landing page (served via GitHub Pages)
├── docs/data/             # JSON index consumed by the landing page
├── tools/                 # helpers (FBX→GLB conversion, index regeneration)
└── renv.lock              # exact R package versions
```

## Reproducing the analysis

### System requirements

- R 4.x or higher (see `renv.lock` for the exact version used)
- RStudio 2023.x or later (recommended but not required)
- LaTeX for rendering the PDF manuscript (MacTeX / MiKTeX / TeX Live, or `tinytex`)

### Quick start

1. Clone the repository and open `manuscript.Rproj` in RStudio.
2. Restore the package environment:
   ```r
   install.packages("renv")  # if not already installed
   renv::restore()
   ```
3. Knit `manuscript.Rmd`. Output: `manuscript.pdf` with all figures, tables, and statistics.

Generating the Bayesian models from scratch takes roughly two hours on an M2 MacBook.

## Documentation

- renv: https://rstudio.github.io/renv/articles/renv.html
- papaja (R Markdown framework used here): https://frederikaust.com/papaja_man/
- Three.js FBXLoader: https://threejs.org/docs/#examples/en/loaders/FBXLoader

## Licence

Code under MIT (see `LICENSE`). Sketch maps and manuscript text © the authors.

## Contact

Jakub Krukar — krukar@uni-muenster.de
