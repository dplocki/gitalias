# Refresh the default branch

This command will remove all potential changes from the default local branch in your repository.
Use with caution.

## Notes

* default branch: `git config init.defaultBranch` (see: [git default-branch](https://github.com/GitAlias/gitalias/blob/7b941c3abbcee391b6bfc4f8d6b8372064245b49/doc/git-default-branch/index.md))
* remove all changes from `main` branch `git checkout main && git fetch origin --prune && git reset --hard origin/main` (see: [git mainly](https://github.com/GitAlias/gitalias/tree/7b941c3abbcee391b6bfc4f8d6b8372064245b49/doc/git-mainly))
