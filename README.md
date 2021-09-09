# setup-python-poetry

This action allows python and poetry to be installed, and the dependencies of the project as well.

## Usage

### Pre-requisites

Create a workflow `.yml` file in your repositories `.github/workflows` directory. An [example workflow](#example-workflow) is available below. For more information, reference the GitHub Help Documentation for [Creating a workflow file](https://help.github.com/en/articles/configuring-a-workflow#creating-a-workflow-file).

### Inputs

- `python-version` - Python version to install.
- `install-args` - Arguments to pass to `poetry install`.

## Example workflow

```yaml
name: CI

on: push

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: myhome-wabash-tech/setup-python-poetry@v1
        with:
          python-version: 3.9

      - name: Lint with isort
        run: poetry run isort --check-only .
```
