# Conda dependency submission action

This repository scans Conda environment.yaml files and uploads the results to the dependency graph. While GitHub does not support alerting on OS-level dependencies, it will alert on any PyPI dependencies that are defined in the environment.yaml. 


### Example workflow

```yaml

name: Conda dependency submission

on:
  workflow_dispatch:
  push:

permissions: 
  id-token: write
  contents: write

jobs:
  dependency-submission:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Conda dependency scanning
        uses: jhutchings1/conda-dependency-submission-action@v0.0.3
```        
