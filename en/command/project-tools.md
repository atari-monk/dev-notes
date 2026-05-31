## Project `project-tools` commands

- [Note](#note)
- [Timer](#timer)
- [Project](#project)
- [Dev Notes](#dev-notes)

First define variables (if stated), then run command.

### Note

#### Print log names

```sh
proj note -p
```

#### Note

- what are you implementing
- any misc info

```sh
log="" && text="" && proj note -l "$log" -t "$text"
```

#### Open log to edit

```sh
log="" && cd /home/atari-monk/atari-monk/project/log/ && code "$log.log"
```

### Timer

#### Pomodoro

```sh
proj timer -o
```

#### Interval

```sh
interval="" && proj timer -t "$interval"
```

### Project

#### Print projects

```sh
find /home/atari-monk/atari-monk/project/ -mindepth 1 -maxdepth 1 -type d -printf '%f\n'
```

#### New doc

```sh
project="" && category="" && name="" && cd /home/atari-monk/atari-monk/project/$project/ && proj docs new -p . -c docs/$category -n $name
```

#### Order file

```sh
project="" && proj docs gen_idx_order -p "/home/atari-monk/atari-monk/project/$project/docs"
```

#### Index file

```sh
project="" && proj docs gen_idx -p "/home/atari-monk/atari-monk/project/$project/docs"
```

#### Get paths

Get all file paths from the `src` directory first, followed by files in the project root, while ignoring `.prettierrc`, `pnpm-lock.yaml`, `.gitignore`, and `.prettierignore`. Each path is prefixed with three spaces. The `\` at the end of each line is the **`sh` line-continuation character**, allowing the command to span multiple lines. The combined output is printed to the terminal and copied to the clipboard.

```sh
cd /home/atari-monk/atari-monk/project/match-pairs/ && \
{

    find src -type f -printf '   %p \\\n'

    find . -maxdepth 1 -type f \
        ! -name '.prettierrc' \
        ! -name 'pnpm-lock.yaml' \
        ! -name '.gitignore' \
        ! -name '.prettierignore' \
        -printf '   %p \\\n'

} | tee >(xclip -selection clipboard)
```

#### Bundle

Bundles all project code and most configs to a prompt. Remove not relevant files to get shorter prompt.

```sh
project="" && cd /home/atari-monk/atari-monk/project/$project/ && \
proj files bundle \
  -o prompt/prompt.md \
  -p prompt/srs.md && \
xclip -selection clipboard < prompt/_prompt.md
```

### Dev Notes

#### New dev-note

```sh
category="" && name="" && cd /home/atari-monk/atari-monk/project/ && proj docs new -p dev-notes -c en/$category -n $name
```

#### Remove order and index files

```sh
cd "/home/atari-monk/atari-monk/project/dev-notes/" && rm -rf order.txt index.md
```

#### Order file

```sh
proj docs gen_idx_order -p "/home/atari-monk/atari-monk/project/dev-notes/"
```

#### Index file

```sh
proj docs gen_idx -p "/home/atari-monk/atari-monk/project/dev-notes/"
```

#### Commit and Push

```sh
repo="/home/atari-monk/atari-monk/project/dev-notes"
git -C "$repo" add . &&
git -C "$repo" commit --amend -m "docs: dev notes" &&
git -C "$repo" push --force origin main
```
