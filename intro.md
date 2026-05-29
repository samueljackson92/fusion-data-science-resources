# Fusion Data Science Resources

A curated collection of notebooks for training data scientists working in fusion energy research.
These materials cover practical techniques for analysing tokamak diagnostic signals, from
time-series classification and shapelet methods to ensemble classifiers trained on real plasma events.

## Notebooks

- [Learning to Label Data with Shapelets](shapelets.ipynb) — use labelled ELM and IRE events to train shapelet-based classifiers on MAST diagnostic signals

## Background

Fusion experiments produce large volumes of high-rate time-series data from hundreds of
diagnostic sensors per shot. Learning to extract physics-meaningful signals from this data —
and to build classifiers that generalise across shots and machines — is a core skill for
fusion data scientists.

The notebooks here use real experimental data from [FAIR MAST](https://github.com/ukaea/fair-mast),
the open dataset from the MAST (Mega Amp Spherical Tokamak) experiment at the
[UK Atomic Energy Authority](https://www.gov.uk/government/organisations/uk-atomic-energy-authority).

## Getting Started

Install dependencies:

```bash
pip install ".[dev]"
pip install git+https://github.com/ukaea/fair-mast-benchmarks.git
```

Build this site:

```bash
pip install ".[book]"
jupyter-book build .
open _build/html/index.html
```
