# Ruff Settings
Public repository containing a standardized ruff configuration


# Installation

## Python packaging configuration

Add the following line to your `pyproject.toml`:

```bash
[tool.ruff]
extend = ".ruff-base.toml"
# Add your local config updates here
```

## Gitignore

Extend your `.gitignore` file by adding:

```bash
.ruff-base.toml
```


## Pre-commit

Add an additional hook to your `.pre-commit-config.yaml` file before the ruff hook:

```bash
  - repo: local
    hooks:
      - id: fetch-ruff-config
        name: Fetch shared ruff config
        entry: bash -c 'curl -sSL https://raw.githubusercontent.com/hema-to/ruff_settings/main/ruff.toml -o .ruff-base.toml'
        language: system
        always_run: true
        pass_filenames: false
```
