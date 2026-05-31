## Commit Message Convention

Structured format for commit messages.

### Format

```
<type>(<scope>): <short description>

[optional body]

[optional footer]
```

### Types

* **feat**: new user-facing feature
* **fix**: bug fix
* **chore**: maintenance (no production code change)
* **docs**: documentation only
* **style**: formatting, missing semicolons, etc. (no logic change)
* **refactor**: code change without feature or bug impact
* **perf**: performance improvements
* **test**: adding or updating tests
* **build**: build system or dependency changes
* **ci**: CI configuration changes

### Scope

Optional; indicates affected area.

Examples:

* `auth` → authentication
* `api` → backend API
* `ui` → frontend components
* `db` → database layer

### Examples

```
feat(auth): add Google OAuth login
fix(api): resolve null pointer in user endpoint
chore(deps): update dependencies
refactor(ui): simplify button logic
docs(readme): update installation steps
```

### Guidelines

* Use imperative mood (“add”, not “added”)
* Keep subject line ≤ 72 characters
* Be specific but concise
* Split unrelated changes into separate commits
* Use body to explain *why*, not *what*