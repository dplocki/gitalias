# Commit prefix

```ini
pcmt = "!f () { git commit -m \"$*\"; }; branch=$(git rev-parse --abbrev-ref HEAD | cut -d'/' -f2 | cut -d'-' -f1-2); f `printf \"[$branch]\"`"
```

## Whole code

```sh
f () {
    git commit -m "$*"
}

branch=$(git rev-parse --abbrev-ref HEAD | cut -d'/' -f2 | cut -d'-' -f1-2)

f `printf "[$branch]"` $*
```

## Notes


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

* The *cutting* code:

    ```sh
    echo "feature/LOREM-124242-ipsum-dolor-sit-amet-23_2323" | cut -d'/' -f2 | cut -d'-' -f1-2
    ```
