## Replace last commit

Replaces the last commit with the current staged snapshot and updates the remote branch history.

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
