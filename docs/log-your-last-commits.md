# Your last commits

Display the list of last commits from given user.

## Whole code

```sh
git log --pretty=format:"%C(yellow)%H %Cgreen%ad %C(cyan) %Cblue%an %Creset %s" --date=format-local:"%Y-%m-%d %H:%M" $*
```

## Notes

* one line commit

  ```sh
  git log --pretty=format:"%h %ad | %an | %s" --date=short
  ```

* filter the users

  ```sh
  git log --author="John Smith"
  ```

* display the colours of the terminal (Bash)

  ```sh
  echo -e "\e[1;31mRed\e[0m \e[1;32mGreen\e[0m \e[1;33mYellow\e[0m \e[1;34mBlue\e[0m \e[1;35mMagenta\e[0m \e[1;36mCyan\e[0m \e[1;37mWhite\e[0m \e[1;30mBlack\e[0m"
  ```

* colours in the logs

  * `%C(reset)`
  * `%C(bold)`
  * `%C(dim)`
  * `%C(underline)`
  * `%C(blink)`
  * `%C(reverse)`
  * `%C(hidden)`
  * `%C(red)`
  * `%C(green)`
  * `%C(yellow)`
  * `%C(blue)`
  * `%C(magenta)`
  * `%C(cyan)`
  * `%C(white)`
  * `%C(black)`

* use colours example:

  ```sh
  git log --pretty=format:"%C(yellow)%h %Cgreen%ad %C(cyan)| %Cblue%an %Creset| %s"
  ```

* full date with hour: `--date=format-local:"%Y-%m-%d %H:%M"`
