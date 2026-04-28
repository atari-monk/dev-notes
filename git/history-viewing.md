## History viewing

### 1. Full commit history

```bash
git log
```

---

### 2. Compact view (one line per commit)

```bash
git log --oneline
```

---

### 3. Graph view (branches + merges)

```bash
git log --oneline --graph --all
```

---

### 4. Limit number of commits

```bash
git log -n 5
```

---

### 5. History for a specific file

```bash
git log path/to/file
```

---

### 6. Show diffs in history

```bash
git log -p
```

---

### 7. Custom format

```bash
git log --pretty=format:"%h - %an, %ar : %s"
```

---

### 8. Filter by author

```bash
git log --author="Your Name"
```

---

### 9. Compare branches/commits

```bash
git log branch1..branch2
```

---

### 10. GUI history

```bash
gitk
```

---

### 11. Follow file across renames

```bash
git log --follow path/to/file
```

---

### 12. Detailed graph view

```bash
git log --oneline --graph --decorate --all
```
