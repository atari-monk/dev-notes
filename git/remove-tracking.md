## Remove tracking

Remove Git tracking (safe method)

```sh
cd /path/to/your/project
ls -a   # optional: confirm .git exists
mv .git .git_backup
```

This disables Git tracking by renaming the repository metadata folder. Your files remain unchanged.

If everything is fine later, you can permanently remove the Git history:

```sh
rm -rf .git_backup
```

After renaming, `git status` will show:

```
fatal: not a git repository (or any of the parent directories): .git
```

---
