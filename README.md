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
      - uses: actions/checkout@v3
      - name: Conda dependency scanning
        uses: jhutchings1/conda-dependency-submission-action@v0.0.2
```        
# License
This project is licensed under the terms of the MIT open source license. Please refer to [MIT](LICENSE.md) for the full terms.
