# GitHub Config

A centralized place for config files used in many GitHub repositories 🛠️

## Why?

If you have a lot of repositories, a small adjustment becomes a huge job to update this everywhere. This process is partly automated with this approach and in the end you only have work on merging the pull requests.

## Shared configuration migration

Personal repositories use [klaasnicolaas/.github](https://github.com/klaasnicolaas/.github) for release policy, dependency presets, labels and inherited community files. Local workflows remain in the packages. The rollout PRs remove the corresponding legacy sync paths before consumer adoption.

This repository remains active for local tooling/workflow files and NIPKaart until those owners complete their template/configuration handover. NIPKaart/.github currently contains only a profile README, so its existing mappings are retained. Do not archive this repository or disable sync while these targets remain. The unused Dependabot file and superseded standalone Python Renovate source are removed.

## How it works

* Common config files are kept in this repository
* When a release is published in this repo, the [Repo File Sync] action is triggered
* PR's are raised in the target repos with the changes, defined in [sync.yml](.github/sync.yml)

## Setting up development environment

This Python project is fully managed using the [Poetry][poetry] dependency
manager.

You need at least:

- Python 3.11+
- [Poetry][poetry-install]

### Installation

Install all packages, including all development requirements:

```bash
poetry install
```

_This project will be installed in non-package mode._

### Pre-commit

This repository uses the [pre-commit][pre-commit] framework, all changes
are linted and tested with each commit. To setup the pre-commit check, run:

```bash
poetry run pre-commit install
```

And to run all checks and tests manually, use the following command:

```bash
poetry run pre-commit run --all-files
```

[Repo File Sync]: https://github.com/marketplace/actions/repo-file-sync-action
[copier]: https://copier.readthedocs.io/en/stable/
[poetry-install]: https://python-poetry.org/docs/#installation
[poetry]: https://python-poetry.org
[pre-commit]: https://pre-commit.com
