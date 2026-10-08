# Road Safety Patterns

A notebook-based exploratory analysis project for studying patterns in road-safety data. The repository organizes the analysis into descriptive, temporal, and geographic notebooks.

## Notebooks

- `DescriptiveAnalysis.ipynb`: descriptive exploration of the available accident data.
- `TimeAnalysis.ipynb`: analysis of temporal patterns.
- `LocationAnalysis.ipynb`: analysis of spatial and location-related patterns.

The notebooks contain the analytical workflow and visualizations. Findings depend on the input data and notebook execution environment.

## Requirements

Python dependencies are listed in `requirements.txt`. Create an isolated environment and install them:

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Run the analyses

Open the notebooks from the repository root with Jupyter:

```bash
jupyter lab
```

Run each notebook from top to bottom. If a notebook expects source data that is not included in the repository, obtain that data through its original source and update the notebook's input path. Review the notebook cells for exact filenames and column requirements.

## Data and interpretation

This repository is an exploratory analysis, not a deployed prediction service. The README does not claim predictive performance or causal conclusions. Check data provenance, geographic coverage, missing values, and notebook assumptions before interpreting or reusing results.

## License

No license file is currently listed. Contact the repository owner before reusing or redistributing this work.
