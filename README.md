# Cookiecutter Research Project Template

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A flexible Cookiecutter template for creating well-structured research project directories in Python. Designed to promote organization and reproducibility across various research domains, including:

*   Data Science & Machine Learning (Classification, Regression)
*   Neuroimaging (BIDS structure awareness, fMRI GLM analyses)
*   Computational Modeling (e.g., Reinforcement Learning)
*   Behavioral Analyses
*   Web-based experiment deployment (optional structure for JS/FastAPI)

## Features

This template provides a standardized layout:

*   **`config/`**: Store configuration files (parameters, settings).
*   **`data/`**: Organized data storage (`raw`, `processed`, `external`), compatible with BIDS in `raw`.
*   **`docs/`**: Project documentation (methods, reports).
*   **`notebooks/`**: Jupyter notebooks for **exploration** and prototyping.
*   **`reports/`**: **Final** notebooks/scripts generating figures/reports from `results/`.
*   **`src/`**: Reusable source code (Python modules/packages).
*   **`scripts/`**: Runnable analysis scripts orchestrating the workflow.
*   **`tests/`**: Unit/integration tests for your source code.
*   **`results/`**: Organized storage for outputs (figures, tables, trained models, statistical maps) grouped by analysis.
*   **`experiment_code/`**: (Optional) Separate directory for data collection code (e.g., PsychoPy, web tasks).
*   Standard files like `README.md`, `requirements.txt`, `environment.yml` (optional).

## Requirements

You need to have Cookiecutter installed:

```bash
pip install cookiecutter
```

## Usage

To use this template to start a new project:

1.  Navigate to the directory where you want to create your project folder.
2.  Run the `cookiecutter` command, pointing it to this repository:

    ```bash
    cookiecutter gh:krkulkarni/cookiecutter-research-project
    ```

3.  Cookiecutter will prompt you for the following information:

    *   `project_name`: The human-readable name of your project (e.g., "My Awesome Research").
    *   `project_slug`: The directory and Python package name (auto-generated from `project_name`, e.g., "my_awesome_research").
    *   `author_name`: Your name.
    *   `author_email`: Your email address.
    *   `description`: A short description of the project.
    *   `version`: Initial project version (e.g., "0.1.0").
    *   `project_url`: URL for the project's repository (defaults based on GitHub username and `project_slug`).
    *   `open_source_license`: Choose a license for the generated project.
    *   `python_interpreter`: Preferred Python command (`python3` or `python`).

4.  A new directory named according to `project_slug` will be created, containing the populated project structure.

## License

The Cookiecutter *template itself* is licensed under the MIT License. The license chosen during the setup (`open_source_license` variable) applies to the *project generated* by this template.

## Contributing

Suggestions and improvements to this template are welcome! Please feel free to open an Issue or Pull Request.
