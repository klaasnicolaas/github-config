# GitHub Config

A centralized place for config files used in many GitHub repositories 🛠️

## Why?

If you have a lot of repositories, a small adjustment becomes a huge job to update this everywhere. This process is partly automated with this approach and in the end you only have work on merging the pull requests.

## How it works

* Common config files are kept in this repository
* When a release is published in this repo, the [Repo File Sync] action is triggered
* PR's are raised in the target repos with the changes, defined in [sync.yml](.github/sync.yml)

[copier]: https://copier.readthedocs.io/en/stable/
[Repo File Sync]: https://github.com/marketplace/actions/repo-file-sync-action
