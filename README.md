# Geoscience Data Science Boilerplate
This is general boilerplate template for geoscience projects.

Geoscience Data Science Boilerplate
==============================

This is general boilerplate template for geoscience projects.

Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    │── pyproject.toml    <- Human-readable project dependencies managed with Poetry
    │── poetry.lock       <- File used by Poetry to install dependencies
    └── .pre-commit-config.yaml <- pre-commit Git hooks


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>

## Installation

### 1. Clone the repository
#### Option 1: Create a repository from the template via GitHub
On the main page of the repository, click **Use this template** and select **Create a new repository**. 
![Screenshot of the "Use this template" button and the dropdown menu expanded to show the "Open in a codespace" option.](https://docs.github.com/assets/cb-77734/mw-1440/images/help/repository/use-this-template-button.webp)

Now simply clone the new project to a new local project directory.
```bash
git clone [new-repository-url]
```

#### Option 2: Clone the boilerplate project
```bash
git clone https://github.com/dluks/geosci-boilerplate.git

cd geosci-boilerplate

# Re-initialize project with new history
rm -rf .git
git init
```

### 2. Install poetry and DVC.
Use `pipx` to install CLI requirements in isolated environments so to avoid dependency conflicts between the CLI tools and the project-specific requirements.
> [!NOTE]
> Omit `dvc` installation if you won't be using DVC for data versioning.

> [!WARNING]
> Update this README with the specific poetry version after installation to avoid conflicts during collaboration (e.g. `pipx install poetry==1.7`)
```bash
pipx install poetry
pipx install dvc
```

 >[!NOTE]
 > If you don't have root access, `condax` (a similar project) can be installed with:
 > ```bash
 > pip install --user condax
 > ```

### 3. Create a virtual environment
> [!NOTE]
> `mamba` is simply a faster implementation of `conda`. If you don't have `mamba` installed, `conda` will also work.

```bash
mamba create -n your-project -c conda-forge python=3.10
mamba activate your-project
```

### 4. Install requirements
This checks to confirm python and conda environment setup. If on Windows, or if you'd simply prefer not to use `make`, you can use `poetry install` instead.
```bash
make requirements
```

### 5. Configure pre-commit Git hooks (optional)
> [!NOTE]
> This project uses `pre-commit` to manage Git hooks. If you'd prefer not to use them, simply remove `pre-commit` with
> ```bash
> poetry remove pre-commit
> ```
```bash
pre-commit install
```
