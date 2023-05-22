# Reusable Workflows

A collection of reusable workflows for Github Actions.

## Available workflows

- [`monorepo-semver-tags.yml`](.github/workflows/monorepo-semver-tags.yml)

This workflow creates and bumps semantic version tags on a per-project basis in a monorepo.

### Usage

```yaml
bump-and-tag:
  permissions:
    contents: write
  uses: andres-rojas/reusable-workflows/.github/workflows/monorepo-semver-tags.yml@main
  with:
    bump: major
    filter: 's/^([A-Za-z0-9-]+)\/.*$/\1/p'
```

To trigger on pull request labels, see [this repo's implementation](./.github/workflows/bump-and-tag.yml).

## Development

### Dev Container

A pre-packaged development environment is provided as a [Development Container](https://containers.dev/).

The [.devcontainer.json](.devcontainer.json) file deploys an Ubuntu environment with the following tools:

- [act](https://github.com/nektos/act)
- [GitHub CLI](https://cli.github.com/)

All [pre-commit hooks](#pre-commit-hooks) are also installed.

#### VS Code

When used via [Visual Studio Code](https://code.visualstudio.com/docs/devcontainers/containers), the following extensions are included:

- [actionlint](https://marketplace.visualstudio.com/items?itemName=arahata.linter-actionlint)
- [GitHub Actions](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-github-actions)

### Pre-Commit Hooks

Pre-commit git hooks are set up and managed via [pre-commit](https://pre-commit.com/).

The [.pre-commit-config.yaml](.pre-commit-config.yaml) file uses the following linters:

- [actionlint](https://github.com/rhysd/actionlint)
- [prettier](https://prettier.io/)
