# Rust pycobertura
This action and sets up pycobertura and runs test on current and previous versions of the repo. Then generates HTML
reports and sticky comments.

## Usage
```yaml
name: Rust

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  coverage:
    name: Code coverage
    runs-on: ubuntu-latest
    steps:
      - name: Generate coverage
        uses: syyyr/rust-pycobertura-action@v2.0.0
        with:
          project_name: <my_project_name>
          cargo_test_arguments: "" # Optional, the default is "--all-features"
          fail_if_worse: "" # Optional, the default is "false"
```
