# Your last commits

Display the list of last commits of current user.

```ini
ylc = !git log --pretty=tformat:'%C(yellow)%H%Creset %C(green)%ad %C(reset)%s' --date=format-local:'%Y-%m-%d %H:%M' --author=$(git config user.name) -n 10
```

Syntax:

```
git ylc
git ylc [git log parameters]
```

## Examples

```
$ git ylc
81b841fc164a97423f17b248bad9c6d43e853fb8 2024-04-03 16:48 Yours last logs: Add notes
4a7b6d88aef13cedf8d7c9ecf4d3ebd763950e3b 2024-04-02 20:52 Log yours last commits: add draft of final solution
ce478bfd86215c10da255112f94c3971c100d94e 2024-04-02 20:43 Add notes for log your last commits
aea2020e9533a85b77693adfc9aba80085f122c8 2024-04-02 19:24 Log your last commits
2e83e3c79bdbd6360d293c49aa5b3e1318b4ec03 2024-03-24 07:50 Create LICENSE
03484bebe806c4574c57afacba423213b0ab5f44 2024-03-24 07:44 Move notes into seperate file
1b2c6c1c37a2e4cd3bc944eb6f99f9f176f68863 2024-03-24 07:37 Start the aiases list
d500b1cb874cece08826e582afcfb7bef6462405 2024-03-24 07:31 Add code for prefix commit
2e0b849cb767670841928f52c72a51ea7f81089c 2024-03-24 07:14 Format up the commit-prefix.md
b0786ffe4bc6736e2cd9a8b12ed239dfbb662e21 2024-03-24 06:57 Extend example template
```

```
$ git ylc -n 1
81b841fc164a97423f17b248bad9c6d43e853fb8 2024-04-03 16:48 Yours last logs: Add notes
```

## Whole code

```sh
git --pretty=tformat:'%C(yellow)%H%Creset %C(green)%ad %C(reset)%s' --date=format-local:'%Y-%m-%d %H:%M' --author=$(git config user.name) -n 10 $@
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
* current user logs: `git log --author="$(git config user.name)"`
