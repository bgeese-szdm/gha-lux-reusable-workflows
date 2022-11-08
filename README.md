# gha-lux-reusable-workflows

- [gha-lux-reusable-workflows](#gha-lux-reusable-workflows)
  - [Available workflows](#available-workflows)
  - [pullrequest](#pullrequest)
    - [Usage](#usage)
  - [release](#release)
    - [Usage](#usage-1)

## Available workflows

## [pullrequest](./.github/workflows/pullrequest.yaml)

Check if changes in a pullrequest are save to merge by running:

-   Lint
-   Build dist
-   Test
-   GraphQL Schema validation

### Usage

Use it in a workflow like this:

```yaml
name: Pullrequest checks
on: pull_request

jobs:
    PR-Checks:
        uses: sueddeutsche/gha-lux-reusable-workflows/.github/workflows/pullrequest.yaml@v1
        secrets:
            NPM_TOKEN: ${{ secrets.NPM_TOKEN }}
```

## [release](./.github/workflows/release.yaml)

Do a semantic release

### Usage

Use it in a workflow like this:

```yaml
name: Release
on:
    push:
        branches: ["main", "beta"]

jobs:
    PR-Checks:
        uses: sueddeutsche/gha-lux-reusable-workflows/.github/workflows/pullrequest.yaml@v1
        secrets:
            NPM_TOKEN: ${{ secrets.NPM_TOKEN }}
```
