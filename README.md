# Diauxic E Coli Simulation

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

An introductory hands-on example to Flux Balance Analysis (FBA), its limitations and corresponding dynamic/kinetic extensions to it. Using the example of E. coli growth on glucose and acetate used to demonstrate [dynamic enzyme constrained Flux Balance Analysis with enzyme change constraints (decFBAecc)](https://doi.org/10.1371/journal.pone.0280077)

> [!NOTE]
> Currently, all work in Jupyter notebook [1.0-tx-init-exploration.ipynb](notebooks/1.0-tx-init-exploration.ipynb).

## Installation
1. You must have git. Clone this repository.

2. This project uses conda/mamba for cleanly managing dependencies/packages. If not yet installed, [install conda](https://docs.conda.io/projects/conda/en/stable/user-guide/getting-started.html#before-you-start) or [mamba](https://mamba.readthedocs.io/en/latest/installation/mamba-installation.html).

3. Enter the root directory of the project where you cloned it to. Then run
    `conda env install -f environment.yaml`
    or
    `mamba env install -f environment.yaml`

4. _For now_, please manually download the data--S1 file, [`growth_medium.xlsx`](https://doi.org/10.1371/journal.pone.0280077.s001), and S4 file, [`fermentation_data.xlsx`](https://doi.org/10.1371/journal.pone.0280077.s004), of [the source paper](https://doi.org/10.1371/journal.pone.0280077).

## Running
Run the notebook [1.0-tx-init-exploration.ipynb](notebooks/1.0-tx-init-exploration.ipynb).

## ___CookieCutter__-inherited_ Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── ==data==
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── ==notebooks==      <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         diaux_coli and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── ~~requirements.txt~~   <- ~~The requirements file for reproducing the analysis environment, e.g.~~
│                         ~~generated with `pip freeze > requirements.txt`~~
├── environment.yml    <- The original requirements file that generated the analysis environment
│                         with `conda env create -f environment.yml`
├── ==environment.yaml==   <- The requirements file for reproducing the analysis environment, e.g.
|                         by running `conda env create -f environment.yaml`
│
├── setup.cfg          <- Configuration file for flake8
│
└── diaux_coli   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes diaux_coli a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── features.py             <- Code to create features for modeling
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```

--------

