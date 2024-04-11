# Refresh the default branch

This command will remove all potential changes from the default local branch in your repository.
Use with caution.

## Notes

* default branch: `git config init.defaultBranch` (see: [git default-branch](https://github.com/GitAlias/gitalias/blob/7b941c3abbcee391b6bfc4f8d6b8372064245b49/doc/git-default-branch/index.md))

    * that is not per repository, but general settings

* the other way for the name of default branch names is command (returning e.g.: `main`)

    ```sh
    git symbolic-ref refs/remotes/origin/HEAD | sed 's@^refs/remotes/origin/@@'
    ```

    * or short version (but returning e.g.: `origin/main`)

        ```sh
        git symbolic-ref refs/remotes/origin/HEAD --short
        ```

  unfortunetly, that can return the old value (previous default branch)

* the other suggestions is command:

   ```sh
   git remote show origin | grep 'HEAD branch' | cut -d' ' -f5
   ```

* remove all changes from `main` branch `git checkout main && git fetch origin --prune && git reset --hard origin/main` (see: [git mainly](https://github.com/GitAlias/gitalias/tree/7b941c3abbcee391b6bfc4f8d6b8372064245b49/doc/git-mainly))
