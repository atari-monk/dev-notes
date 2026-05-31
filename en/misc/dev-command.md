## Dev Commands

- [Note](#note)
- [Timer](#timer)
- [Projects](#projects)
- [Docs](#docs)
- [Tree](#tree)
- [Path](#path)

First define variables (if stated), then run command.

### Note

Print log names:

```sh
proj note -p
```

Note:

- what are you implementing
- any misc info

```sh
log="" && text="" && proj note -l "$log" -t "$text"
```

Open log to edit:

```sh
log="" && cd /home/atari-monk/atari-monk/project/log/ && code "$log.log"
```

### Timer

Use to mesure pomodoro

```sh
proj timer -o
```

any time interval

```sh
interval="" && proj timer -t "$interval"
```

### Projects

Print projects:

```sh
find /home/atari-monk/atari-monk/project/ -mindepth 1 -maxdepth 1 -type d -printf '%f\n'
```

### Docs

#### Dev Notes

Remove order and index files:

```sh
cd "/home/atari-monk/atari-monk/project/dev-notes/" && rm -rf order.txt index.md
```

Order file:

```sh
cd "/home/atari-monk/atari-monk/project/dev-notes/" && proj docs gen_idx_order -p .
```

Index file:

```sh
cd "/home/atari-monk/atari-monk/project/dev-notes/" && proj docs gen_idx -p .
```

Commit and Push:

```sh
cd "/home/atari-monk/atari-monk/project/dev-notes/" && git add . && git commit --amend -m "docs: dev notes" && git push --force origin main
```

#### Project

Order file:

```sh
project="" && cd "/home/atari-monk/atari-monk/project/$project/" && proj docs gen_idx_order -p docs
```

Index file:

```sh
project="" && cd "/home/atari-monk/atari-monk/project/$project/" && proj docs gen_idx -p docs
```

### Tree

Print file tree using ubuntu command.

```sh
project="" && path="" && cd "/home/atari-monk/atari-monk/project/$project/" && tree $path
```

### Path

Prints current full path:

```sh
realpath .
```
