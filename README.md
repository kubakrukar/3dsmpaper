# 3D sketch maps paper

## Overview

This repository contains all data, code, and materials necessary to reproduce all findings reported in the manuscript. All file paths are relative, and the analysis can be reproduced by following the step-by-step instructions below.

Code and text are integrated: In order to reproduce any figure or result from the manuscript, locate the relevant code chunk in the manuscript.Rmd file.

## System Requirements

- **R version**: 4.x.x or higher (check `renv.lock` for exact version used)
- **RStudio**: Version 2023.x or higher (recommended but not required)
- **LaTeX**: Required for generating the PDF manuscript
  - macOS: MacTeX (https://www.tug.org/mactex/)
  - Windows: MiKTeX (https://miktex.org/)
  - Linux: TeX Live (`sudo apt-get install texlive-full`)
- **Operating System**: Cross-platform (tested on macOS)

## Quick Start

1. **Clone repository and open project**
   Double-click `manuscript.Rproj` to open in RStudio. In the 'Files' tab, `open manuscript.Rmd`

2. **Restore R packages**
```r
   install.packages("renv")  # if needed (not required if you have a recent RStudio)
   renv::restore()           # installs exact package versions
```

3. **Reproduce all results**
```r
   # Knit the manuscript to reproduce all figures, tables, and statistics
   rmarkdown::render("manuscript.Rmd") # or press the "knit" button in RStudio
```
   
   Output: `manuscript.pdf` with all results, including tables and figures.

## Documentation

- **renv documentation** (in case of issues with restoring correct package versions): https://rstudio.github.io/renv/articles/renv.html
- **papaja documentation** (detailed instructions on how code and text are integrated in a single .Rmd file): https://frederikaust.com/papaja_man/

All file paths are relative. All code is commented. No manual modifications needed.

## Runtime

Generating Bayesian models may take up to ca. 2 hours in total (for all models in the repository) on an M2 Macbook.

## Troubleshooting

**Package installation fails**: `renv::clean()` then `renv::restore()`  
**LaTeX errors**: Install tinytex: `tinytex::install_tinytex()`

## Contact

anonymised