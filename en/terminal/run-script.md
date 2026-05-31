## Run Script

Smarter way to run scripts in terminal:

Define script to run in a variable

```sh
script="/home/atari-monk/atari-monk/project/scripts/scripts/python/assemble_prompt.py"
```

Define script input in variables

```sh
prompt="/home/atari-monk/atari-monk/project/prompts/prompts/explain-code.md"
```

```sh
map="/home/atari-monk/atari-monk/project/scripts/.config/prompt-map.json"
```

Run script

```sh
python3 "$script" "$prompt" "$map"
```