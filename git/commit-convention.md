## Commit Conventions

### Contents
- [Minimalist](#minimalist)
- [Tags](#tags)

---

### Minimalist

**Format:**

```text
<type> <description>   (type: add | update | fix | remove | refactor)
```

**Examples:**

```text
add user login endpoint
update dashboard layout for mobile
fix crash on empty form submission
remove deprecated payment method
refactor API response handling
```

---

#### Rule of thumb

* **add** → new thing
* **fix** → broken thing
* **update** → improve/change existing behavior
* **remove** → delete something
* **refactor** → restructure without behavior change

---

#### Use in my projects

Project tech-notes

```text
add note commit-convention
add readme file
add main index
update note commit-convention
update readme file
add note replace-last
add note remove-last
add note remove-tracking
add note history-viewing
add note table-of-contents
update note replace-last
update main index
add note blog-post
update note history-viewing
add note rename-repo
update note history-viewing
rename note blog-post to note
```

Project misc-notes

```text
add readme file
add note movie-review
add note video-review
add custom title
add notes movie and video review in pl
fix note video-review
update main index
fix review notes stucture
add link notes collection
```

---

That’s enough structure to stay consistent without turning commits into a discipline exercise.

[Contents](#contents)

### Tags

Project-specific convention, adds new semantic tags used in this project

**Format:**

```text
<type>: <description>   (type: initial | chore | feat)
```

**Rules:**

- **initial** → first project setup / baseline state
- **chore** → maintenance, refactors, structure cleanup, config changes
- **feat** → new functionality or user-facing features

---

#### Rule of thumb

* **initial** → first snapshot of the project
* **chore** → internal improvements, cleanup, restructuring
* **feat** → anything that adds or changes user-visible functionality

---

#### Use in my projects

Project cv

```text
initial commit with cleaned data, code and styling
chore: refactored project structure
chore: established simpler structure fit for this project
feat: upload photo button
feat: page to download json schema file
feat: integrated main and schema pages
feat: move data load button to photo container and make btns style consistent
feat: tweak experience presentation, small refactor
chore: remove obsolete log data
chore: add gitignore
```

---

This keeps the system lightweight while still scaling beyond basic CRUD-style commit labels.

[Contents](#contents)