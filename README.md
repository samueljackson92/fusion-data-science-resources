# Fusion Data Science Resources

A curated collection of data science notebooks for training fusion energy researchers.
The materials focus on practical techniques for analysing tokamak diagnostic signals,
building event classifiers, and working with the open [FAIR MAST](https://github.com/ukaea/fair-mast) dataset.

## Notebooks

| Notebook | Topic |
|---|---|
| [Shapelets](shapelets.ipynb) | Learning to label plasma events (ELMs, IREs) using shapelet-based classifiers |

## Setup

**Python 3.12+** is required. Install dependencies with:

```bash
# Install core + dev dependencies
pip install ".[dev]"

# Install the FAIR MAST benchmarks library (not on PyPI)
pip install git+https://github.com/ukaea/fair-mast-benchmarks.git
```

Then start JupyterLab:

```bash
jupyter lab
```

## Building the Book

This project is a [Jupyter Book](https://jupyterbook.org). To build the HTML site locally:

```bash
pip install ".[book]"
jupyter-book build .
open _build/html/index.html
```

## Topics Covered

- **Shapelet-based classification** — extracting characteristic subsequences from labelled plasma events and using them as features for a Random Forest classifier
- **DTW distance** — Dynamic Time Warping for comparing time-series subsequences
- **Sliding window transforms** — converting continuous signals into windowed feature matrices
- **Multi-channel extension** — applying the same approach to multi-variate diagnostic signals (IRE events)
- **Aeon integration** — using the `SASTClassifier` from the [aeon](https://www.aeon-toolkit.org) library for automated shapelet selection

## Data

Notebooks use experimental data from the **MAST** (Mega Amp Spherical Tokamak) experiment at
UKAEA Culham. Data is accessed via the `fair_mast_benchmarks` library, which loads labelled
shot datasets (ELM peaks, IRE events) in a standard format.

## License

MIT — see [LICENSE](LICENSE).
