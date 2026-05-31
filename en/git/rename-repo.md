## Rename Repo

### Contents

* [Rename Repository on GitHub](#rename-repository-on-github)
* [Update Local Repository](#update-local-repository)

  * [Verify Changes](#verify-changes)
* [Rename Local Folder (Optional)](#rename-local-folder)

---

### Rename Repository on GitHub

```bash
# No CLI required — done in browser:

# 1. Go to your repo on GitHub
# 2. Click "Settings"
# 3. Change "Repository name"
# 4. Click "Rename"
```

[Contents](#contents)

---

### Update Local Repository

```bash
# Check current remote
git remote -v

# Change remote URL (HTTPS)
git remote set-url origin https://github.com/<USERNAME>/<NEW_REPO_NAME>.git

# OR (SSH)
git remote set-url origin git@github.com:<USERNAME>/<NEW_REPO_NAME>.git
```

[Contents](#contents)

#### Verify Changes

```bash
# Confirm new remote URL
git remote -v

# Test connection
git fetch

# Push to confirm everything works
git push
```

[Contents](#contents)

---

### Rename Local Folder (Optional) <a id="rename-local-folder"></a>

```bash
# Go one level up
cd ..

# Rename folder
mv <OLD_REPO_NAME> <NEW_REPO_NAME>

# Enter renamed folder
cd <NEW_REPO_NAME>
```

[Contents](#contents)

---
