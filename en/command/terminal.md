## Terminal (Ubuntu) Command

### Git log

Git history doc for a project:

````sh
project="" && cd /home/atari-monk/atari-monk/project/$project/ && \
{
  echo '## Git History'
  echo
  echo '```text'
  git log --reverse --format='%s' --all
  echo '```'
} > docs/git-history.md
````

### Project structure

Project structure doc for a project:

````bash
project="" && \
{
  echo "## Project \`$project\` structure"
  echo
  echo '```text'
  tree -a -I '.git|node_modules|__pycache__|.venv|*.egg-info'
  echo '```'
} > /home/atari-monk/atari-monk/project/$project/docs/project-structure.md
````

To install `tree`:

```bash
sudo apt install tree -y
```

### Timer

Ubuntu terminal commands for timers.

#### Test it — 5 seconds

5-second timer with the log stored in the project's `docs/timer.log`:

```bash
project=""

(
    cd "/home/atari-monk/atari-monk/project/$project/" || exit 1

    s=$(date '+%Y-%m-%d %H:%M:%S')
    echo "Start: $s" >> docs/timer.log

    sleep 5s

    e=$(date '+%Y-%m-%d %H:%M:%S')
    echo "End: $e" >> docs/timer.log

    notify-send "⏰ Timer finished!" "5 seconds are up!"
    paplay /usr/share/sounds/freedesktop/stereo/alarm-clock-elapsed.oga
) >/dev/null 2>&1 & disown
```

#### Pomodoro — 25 minutes

25-minute timer with the log stored in the project's `docs/timer.log`:

```bash
project=""

(
    cd "/home/atari-monk/atari-monk/project/$project/" || exit 1

    s=$(date '+%Y-%m-%d %H:%M:%S')
    echo "Start: $s" >> docs/timer.log

    sleep 25m

    e=$(date '+%Y-%m-%d %H:%M:%S')
    echo "End: $e" >> docs/timer.log

    notify-send "⏰ Timer finished!" "25 minutes are up!"
    paplay /usr/share/sounds/freedesktop/stereo/alarm-clock-elapsed.oga
) >/dev/null 2>&1 & disown
```

### Files operations

#### Read timestamps

```bash
cat /docs/timer.log
```

#### Delete log

```bash
rm /docs/timer.log
```

#### Clear log without deleting the file

```bash
> /docs/timer.log
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
