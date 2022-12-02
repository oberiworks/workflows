# Workflows

## A collection of re-usable workflows

![Pre-Commit-Enabled]
![Validate]

This repository is pre-commit enabled:

1) install pre-commit
2) run pre-commit install

---

### workflows

> detect-secrets

Scans all files for potential secrets using the pre-commit detect-secrets hook.
To use this workflow a repository must have a .secrets.baseline file in the root.

Usage:

```yaml
jobs:
  call-detect-secrets:
    uses: oberiworks/workflows/.github/workflows/detect-secrets.yml@main
```

> validate-code

General code validation with switchable linters.

Example usage: Dockerfile lint only using Dockerfile in the root.

```yaml
jobs:
  call-validate-code:
    uses: oberiworks/workflows/.github/workflows/validate-code.yml@main
    with:
      dockerlint: true
```

Example usage: Dockerfile lint only using custom Dockerfile and other linters.

```yaml
jobs:
  call-validate-code:
    uses: oberiworks/workflows/.github/workflows/validate-code.yml@main
    with:
      dockerlint: true
      dockerfile: "./some/path/Dockerfile.build"
      markdownlint: true
      workflowlint: true
      yamllint: true
```

Available linters:

| Linter       | Optional parameters               |
|:-------------|:----------------------------------|
| dockerlint   | dockerfile - path to a Dockerfile |
| markdownlint |                                   |
| rustlint     |                                   |
| workflowlint |                                   |
| yamllint     |                                   |

> validate-comits

Commit validation.

Usage:

```yaml
jobs:
  call-validate-commits:
    uses: oberiworks/workflows/.github/workflows/validate-commits.yml@main
```

[Pre-Commit-Enabled]: https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white
[Validate]: https://github.com/oberiworks/workflows/workflows/Validate/badge.svg
