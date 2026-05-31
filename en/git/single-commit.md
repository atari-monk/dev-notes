## Single commit history

This repository is treated as a personal knowledge database.  
It does not require a chronological development history.

Maintain a single-commit history using:

Set msg variable with any preferred commit message.  
Sugestion: `docs: dev notes database` or `docs: misc notes database` or `docs: prompts database`

```sh
msg=""
```

Commands:

```sh
git add . && git commit --amend -m "$msg" && git push --force origin main
```