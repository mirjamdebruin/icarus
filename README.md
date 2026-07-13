# Icarus — Chemometric Analysis of GC-MS and LC-MS Data

Chemometric and forensic-comparison analysis of chemical samples measured by
GC-MS and LC-MS. The notebooks import mass-spectrometry feature tables, clean
and normalise them, and apply a range of chemometric methods (PCA, LDA, t-SNE,
hierarchical clustering) together with a likelihood-ratio (LR) framework to
investigate linkages between samples.

## Overview

The analysis focuses on samples containing DIMP, DC and IPA. Feature tables are
produced by external tools (mzmine for GC-MS, Compound Discoverer for LC-MS),
imported here, and evaluated to quantify the strength of evidence for a common
source using likelihood ratios via the [`lir`](https://pypi.org/project/lir/)
library.

## Notebooks

| Notebook | Description |
| --- | --- |
| [Icarus_260616_GCMS.ipynb](Icarus_260616_GCMS.ipynb) | GC-MS data import, clean-up, chemometrics and LR analysis. |
| [Icarus_260629_LCMS.ipynb](Icarus_260629_LCMS.ipynb) | LC-MS data import, clean-up, chemometrics and LR analysis. |
| [NFI_practitioners_guide_glass.ipynb](NFI_practitioners_guide_glass.ipynb) | Worked example following the NFI practitioners' guide (glass).

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
example, the GC-MS notebook reads `data/mzmine-results-GCMS.xlsx`. Place the
required export files in `data/` before running the notebooks.

## Notes

- Figures produced by the notebooks are written to `img/`.
- Result data frames are written to `df/`.