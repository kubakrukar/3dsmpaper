# 3D sketch maps paper

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20187706.svg)](https://doi.org/10.5281/zenodo.20187706)

Code, data, and sketch-map gallery for:

> Krukar, J., Aly, A., Baecker, L., Heming, L., Zhao, J., & Schwering, A. *3D Environments Require 3D Visualisations: The Limitations of 2D Sketch Maps in Capturing Spatial Knowledge.* International Journal of Geographical Information Science (under revision).

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

Generating the Bayesian models from scratch takes roughly two hours on an M2 MacBook; cached fits live in `models/` (gitignored — regenerate by knitting).

## Landing page (GitHub Pages)

The repository ships with a self-contained landing page at `index.html` summarising the problem, method, results, and offering a side-by-side 2D / 3D viewer for every sketch map. The 3D viewer uses Three.js with `FBXLoader` and runs entirely in the browser — no build step.

**To publish it via GitHub Pages:**

1. Push the repository to GitHub.
2. *Repository → Settings → Pages*. Set *Source* to *Deploy from a branch*, branch `main`, folder `/ (root)`. Save.
3. After about a minute the site is live at `https://<user>.github.io/<repo>/`.

The page reads `docs/data/sketchmaps.json`, which lists every participant and their files. If you add, remove, or rename sketches, regenerate it:

```bash
python3 tools/generate_sketchmap_index.py
```

### Optional: convert FBX to GLB for faster loading

FBX files from Gravity Sketch are large (5–50 MB each). Converting them to Draco-compressed GLB typically shrinks them 5–10× and the page will load them in preference to the FBX. Run with Blender's bundled Python:

```bash
blender --background --python tools/convert_fbx_to_glb.py
python3 tools/generate_sketchmap_index.py   # refresh the index
```

The FBX files stay in place for archival purposes.

## DOI / Zenodo deposit

The repository is configured for automatic archival on Zenodo on every GitHub Release:

1. Log in to [Zenodo](https://zenodo.org/) with your GitHub account.
2. Go to *Settings → GitHub*, find this repository, and flip the switch to **On**.
3. On GitHub, create a release (`v1.0.0`, etc.).
4. Zenodo mints a versioned DOI plus a concept DOI that always resolves to the latest version. Update the badge at the top of this README with the concept DOI.

If the dataset grows past GitHub's 1 GB soft limit, host the heavier sketch-map files on Zenodo (no individual-file size cap) and point the landing page at the Zenodo URLs in `docs/data/sketchmaps.json`.

## Documentation

- renv: https://rstudio.github.io/renv/articles/renv.html
- papaja (R Markdown framework used here): https://frederikaust.com/papaja_man/
- Three.js FBXLoader: https://threejs.org/docs/#examples/en/loaders/FBXLoader

## Licence

Code under MIT (see `LICENSE`). Sketch maps and manuscript text © the authors.

## Contact

Jakub Krukar — krukar@uni-muenster.de
