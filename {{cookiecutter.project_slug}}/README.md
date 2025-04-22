# {{ cookiecutter.project_name }}

[![License: {{ cookiecutter.open_source_license }}](https://img.shields.io/badge/License-{{ cookiecutter.open_source_license.replace('-', '--') }}-blue.svg)](https://opensource.org/licenses/{{ cookiecutter.open_source_license }})
<!-- You can add more badges here, e.g., for build status, DOI, etc. -->

{{ cookiecutter.description }}

**Version:** `{{ cookiecutter.version }}`

**Author:** {{ cookiecutter.author_name }}

**Project Repository:** [{{ cookiecutter.project_url }}]({{ cookiecutter.project_url }})

**License:** This project is licensed under the {{ cookiecutter.open_source_license }} License - see the LICENSE file for details.

---

## Overview

*(Provide a more detailed overview of the research question, goals, and methods here.)*

---

## Project Structure
```
ProjectName/
├── README.md             # High-level overview, setup, how to run analyses, link to docs
├── requirements.txt      # Python dependencies (pip)
├── environment.yml       # Alternative/conda dependencies (optional)
├── config/               # Configuration files (parameters, settings)
│   └── main_config.yaml  # Example main configuration
│   └── analysis_params.yaml # Example parameters for specific analyses
├── data/                 # Project data (consider .gitignore for large files/privacy)
│   ├── raw/              # Original, immutable data. **For BIDS, this IS the BIDS dir or contains it.**
│   │   └── README.md     # Describe sources, structure (mention BIDS if applicable)
│   ├── processed/        # Intermediate data (e.g., preprocessed fMRI, feature matrices)
│   │   └── README.md     # Describe processing steps and structure
│   └── external/         # Data from external sources (optional)
│       └── README.md
├── docs/                 # Detailed documentation (reports, methods descriptions, protocols)
│   └── project_methods.md # Example documentation
├── notebooks/            # **Exploratory** analysis, prototyping, quick visualizations (temporary/informal)
│   ├── 01_data_exploration.ipynb
│   └── 02_model_prototyping.ipynb
├── reports/              # **Final** notebooks/scripts generating figures/reports from results/
│   └── generate_paper_figures.ipynb # Example: Uses data from results/
├── src/                  # Core reusable source code (functions, classes)
│   ├── __init__.py       # Makes src a Python package
│   ├── preprocessing.py  # Example: data cleaning, BIDS processing functions
│   ├── analysis.py       # Example: GLM setup, ML model definitions, comp model logic
│   ├── utils.py          # Example: helper functions
│   └── viz.py            # Example: plotting functions used by scripts/reports
├── scripts/              # Top-level **runnable scripts** to execute analysis pipelines
│   ├── 01_preprocess_data.py # Example: uses src/preprocessing.py
│   ├── 02_run_glm_analysis.py # Example: uses src/analysis.py, saves to results/
│   ├── 03_train_ml_model.py   # Example: uses src/analysis.py, saves to results/
│   ├── 04_fit_comp_models.py  # Example: uses src/analysis.py, saves to results/
│   └── README.md         # Describe the purpose and recommended order of scripts
├── tests/                # Unit and integration tests for src/ code
│   ├── __init__.py
│   └── test_preprocessing.py # Example test file
├── results/              # **Output from analysis scripts** (figures, tables, models, stats maps)
│   ├── analysis_name_1/  # **Subdir per major analysis** (e.g., glm_group_level, svm_classification)
│   │   ├── figures/
│   │   ├── tables/
│   │   ├── models/       # e.g., trained ML models, fitted comp model params
│   │   ├── stats_maps/   # e.g., fMRI contrast maps
│   │   └── README.md     # Describe the analysis and its outputs within this folder
│   └── analysis_name_2/  # e.g., computational_modeling_comparison
│       └── README.md
└── experiment_code/ # Code for data collection (e.g., PsychoPy, JS/FastAPI task)
    ├── frontend/         # JS/HTML/CSS (if web-based)
    ├── backend/          # Python/FastAPI server (if web-based)
    ├── requirements.txt  # Task-specific Python dependencies (if applicable)
    ├── package.json      # Task-specific JS dependencies (if applicable)
    └── README.md         # Setup and deployment instructions for the task
```

---

## Setup Instructions

1.  **Clone the repository:**
    ```bash
    git clone {{ cookiecutter.project_url }}
    cd {{ cookiecutter.project_slug }}
    ```

2.  **Create and activate a virtual environment using `conda` or `mamba` (if using `environment.yml`):**
    ```bash
    mamba env create -f environment.yml
    mamba activate <your_env_name>
    ```

3.  **Install dependencies using `pip`:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **(Optional) Configure:** Modify files in the `config/` directory as needed for your specific setup (e.g., data paths, parameters).

---

## How to Run Analyses

*(Explain the typical workflow. This often involves running scripts sequentially.)*

Example:
```bash
# Ensure your virtual environment is activated
cd {{ cookiecutter.project_slug }}

# Run the preprocessing script (adjust paths/configs if needed)
{{ cookiecutter.python_interpreter }} scripts/01_preprocess_data.py

# Run a specific analysis (example)
{{ cookiecutter.python_interpreter }} scripts/02_run_glm_analysis.py

# Check the outputs in the results/ directory
ls results/analysis_name_1/
