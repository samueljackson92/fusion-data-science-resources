# Fusion Data Science Resources

A curated collection of data science notebooks for training fusion energy researchers.
The materials focus on practical techniques for analysing tokamak diagnostic signals,
building event classifiers, and working with the open [FAIR MAST](https://github.com/ukaea/fair-mast) dataset.

## Notebooks

| Notebook | Topic |
|---|---|
| [Shapelets](shapelets.ipynb) | Learning to label plasma events (ELMs, IREs) using shapelet-based classifiers |
| [Triple Product](triple_product.ipynb) | Computing the fusion triple product (n × T × τ) for MAST shot 30420 |

## Setup

**Python 3.12+** and [uv](https://docs.astral.sh/uv/) are required. Install dependencies with:

```bash
uv sync
```

Also install the FAIR MAST benchmarks library (not on PyPI):

```bash
uv run pip install git+https://github.com/ukaea/fair-mast-benchmarks.git
```

Then start JupyterLab:

```bash
uv run --extra dev jupyter lab
```

## Building the Book

This project is a [Jupyter Book](https://jupyterbook.org) (v2, powered by MyST). To build and preview the site locally:

```bash
# Build once
uv run --extra book jupyter-book build

# Build and serve with live reload
uv run --extra book jupyter-book start
```

The site will be available at http://localhost:3002.

## Topics Covered

- **Shapelet-based classification** — extracting characteristic subsequences from labelled plasma events and using them as features for a Random Forest classifier
- **DTW distance** — Dynamic Time Warping for comparing time-series subsequences
- **Sliding window transforms** — converting continuous signals into windowed feature matrices
- **Multi-channel extension** — applying the same approach to multi-variate diagnostic signals (IRE events)
- **Aeon integration** — using the `SASTClassifier` from the [aeon](https://www.aeon-toolkit.org) library for automated shapelet selection
- **Fusion triple product** — computing n × T × τ from MAST equilibrium and summary diagnostics using Zarr-format shot data

## Data

Notebooks use experimental data from the **MAST** (Mega Amp Spherical Tokamak) experiment at
UKAEA Culham. Data is accessed via the `fair_mast_benchmarks` library, which loads labelled
shot datasets (ELM peaks, IRE events) in a standard format. The triple product notebook reads
shot data directly from a Zarr store.

## License

MIT — see [LICENSE](LICENSE).
