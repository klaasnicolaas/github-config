# GitHub Config

A centralized place for config files used in many GitHub repositories 🛠️

## Why?

If you have a lot of repositories, a small adjustment becomes a huge job to update this everywhere. This process is partly automated with this approach and in the end you only have work on merging the pull requests.

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

Install all packages, including all development requirements:

```bash
poetry install
```

_This project will be installed in non-package mode._

Poetry creates by default an virtual environment where it installs all
necessary pip packages, to enter or exit the venv run the following commands:

```bash
poetry shell
exit
```

Setup the pre-commit check, you must run this inside the virtual environment:

```bash
pre-commit install
```

*Now you're all set to get started!*

As this repository uses the [pre-commit][pre-commit] framework, all changes
are linted and tested with each commit. You can run all checks and tests
manually, using the following command:

```bash
poetry run pre-commit run --all-files
```

[Repo File Sync]: https://github.com/marketplace/actions/repo-file-sync-action
[copier]: https://copier.readthedocs.io/en/stable/
[poetry-install]: https://python-poetry.org/docs/#installation
[poetry]: https://python-poetry.org
[pre-commit]: https://pre-commit.com
