# Icarus — Chemometric Analysis of GC-MS and LC-MS Data

Chemometric and forensic-comparison analysis of chemical samples measured by
GC-MS and LC-MS. This notebook imports mass-spectrometry data and apply a range of chemometric methods (PCA, HCA) 
together with a likelihood-ratio (LR) framework to investigate linkages between samples.

## Overview

The analysis focuses on samples containing DIMP, DC and IPA. Feature tables are
produced by external tools (mzmine for GC-MS, Compound Discoverer for LC-MS),
imported here, and evaluated to quantify the strength of evidence for a common
source using likelihood ratios via the [`lir`](https://pypi.org/project/lir/)
library.

## Project structure

```
.
├── data/     # Raw input data (mzmine / Compound Discoverer exports, sample names)
├── df/       # Intermediate/processed data frames
├── img/      # Generated figures
└── *.ipynb   # Analysis notebooks
```

## Getting started

This project uses [uv](https://docs.astral.sh/uv/) for environment and
dependency management.

```powershell
# Create the virtual environment and install dependencies from the lockfile
uv sync
```

Then open any notebook in VS Code (or run `jupyter lab`) and select the
`.venv` kernel.

## Data

Input files are expected in the `data/` folder (relative to the notebook). For
example, the GC-MS notebook reads `data/GCMS_widetable_corr_public.csv`. Place the
required export files in `data/` before running the notebooks.

## Notes

- Figures produced by the notebooks are written to `img/`.
- Result data frames are written to `df/`.
