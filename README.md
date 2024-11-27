# tf_test




# Project Organization

```
tf_test/
├── LICENSE                     # Open-source license if one is chosen
├── README.md                   # The top-level README for developers using this project.
├── mkdocs.yml                  # mkdocs-material configuration file.
├── pyproject.toml              # Project configuration file with package metadata for
│                                   tf_test and configuration for tools like ruff
├── uv.lock                     # The lock file for reproducing the production environment, e.g.
│                                   generated with `uv sync`
├── configs                     # Config files (models and training hyperparameters)
│   └── model1.yaml
│
├── data
│   ├── external                # Data from third party sources.
│   ├── interim                 # Intermediate data that has been transformed.
│   ├── processed               # The final, canonical data sets for modeling.
│   └── raw                     # The original, immutable data dump.
│
├── docs                        # Project documentation.
│
├── models                      # Trained and serialized models.
│
├── notebooks                   # Jupyter notebooks.
│
├── references                  # Data dictionaries, manuals, and all other explanatory materials.
│
├── reports                     # Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures                 # Generated graphics and figures to be used in reporting.
│
├── pyproject.toml              # The pyproject.toml file for reproducing the analysis environment.
├── src/tests                   # Unit test files.
│
└── src/tf_test      # Source code for use in this project.
    │
    ├── __init__.py             # Makes tf_test a Python module
    │
    ├── cli.py                  # Default CLI program
    │
    ├── data                    # Data engineering scripts.
    │
    ├── models                  # ML model engineering (a folder for each model).
    │
    └── visualization           # Scripts to create exploratory and results oriented visualizations.
```

# For Developers

## Whether to use `package`

This determines if the project should be treated as a Python package or a "virtual" project.

A `package` is a fully installable Python module,
while a virtual project is not installable but manages its dependencies in the virtual environment.

If you don't want to use this packaging feature,
you can set `tool.uv.package = false` in the pyproject.toml file.
This tells `uv` to handle your project as a virtual project instead of a package.

## Initialize package
### Install Python (latest)
```
uv python install
```

### First Sync for predefined packages
```
uv sync
```

## Install Packages
### Install packages
```
uv sync --frozen
```

### Install dev packages
```
uv sync --all-extras --dev
```

## Testing
### Run tests
```
uv run pytest
```

## Development
### Linting
```
uvx ruff check --fix .
```

### Formatting
```
uvx ruff fmt
```

### Run pre-commit
```
uvx pre-commit run --all-files
```

### Build package
```
uv build
```

## Documentation

### Serve Document
```
uv run mkdocs serve
```

### Build Document
```
uv run mkdocs build
```

## Container
### Build Docker Image (from source)

[ref. uv docs](https://docs.astral.sh/uv/guides/integration/docker/#installing-a-project)

```
docker build -t TAGNAME -f Dockerfile.source
```

### Build Docker Image (from package)

[ref. uv docs](https://docs.astral.sh/uv/guides/integration/docker/#non-editable-installs)

```
docker build -t TAGNAME -f Dockerfile.package
```

### Run Docker Container
```
docker run --gpus all -p 8000:8000 my-production-app
```

# References
* [Packaging Python Projects](https://packaging.python.org/tutorials/packaging-projects/)
* [Python Packaging User Guide](https://packaging.python.org/)
