# A collection of re-usable workflows

## workflows

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
