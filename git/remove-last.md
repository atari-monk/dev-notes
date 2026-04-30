## Remove last commit

Best used in single-developer workflows, or when you are sure no one else has based work on this branch, since it rewrites shared history.

```sh
git reset --hard HEAD~1
git push origin main --force
```

This moves the branch pointer back by one commit; the commit is no longer referenced by the branch history.

### Options

| Command             | Commit history        | Working tree  | Staging area           |
| ------------------- | --------------------- | ------------- | ---------------------- |
| `--soft`            | not part of branch history | unchanged     | **kept (staged)**      |
| `--mixed` (default) | not part of branch history               | unchanged     | **cleared (unstaged)** |
| `--hard`            | not part of branch history               | **discarded** | **discarded**          |

`git push --force` - Overwrite the remote branch unconditionally.  
`git push --force-with-lease` - Overwrite remote only if no one else has pushed since you last fetched. Safer for team work.  

---

### One important alternative (often safer)

If your goal is “undo last commit but keep history clean” in shared branches:

```sh
git revert HEAD
git push
```

This creates a new commit that undoes the previous one, without rewriting history.

---
