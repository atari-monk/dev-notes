## History viewing

### Full Commit history, reverse, only messages

```bash
git log --reverse --pretty=format:"%s"
```

---

### Commit history for specific day, reverse, only messages

```bash
git log --since="2026-04-28 00:00" --until="2026-04-28 23:59" --reverse --pretty=format:"%s"
```

---

### Commit history for specific day, with original date, reverse, only messages

This uses author date.  
After rebase commit date is overwritten with rebase date.  
Original date remains in author date.  

```bash
git log --reverse --pretty=format:"%ad %s" --date=short | sed -n 's/^2026-04-28 //p'
```

---