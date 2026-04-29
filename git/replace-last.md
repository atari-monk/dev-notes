## Replace last commit

Replaces the last commit with a new commit built from the current staged snapshot  
(which initially matches the previous commit, so unchanged files are preserved),  
and updates the remote branch history.

### All

```bash
git add . && git commit --amend -m "commit msg" && git push --force origin main
```

I use this when I want to include all current changes in the amended commit.

---

### Selected

```bash
git commit --amend -m "commit msg" && git push --force origin main
```

I use this after staging only selected changes.

---
