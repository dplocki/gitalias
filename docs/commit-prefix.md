# Commit prefix


# Notes


* The current branch, can be taken by:

    ```sh
    git rev-parse --abbrev-ref HEAD
    ```

* The code which may be used for tests:

    ```sh
    f () {
        touch a.txt
        git add a.txt
        git commit -m "$*"
        git lg -n 3
        git undo-commit-hard
    }
    ```
