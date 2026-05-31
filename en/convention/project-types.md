## Project types

Projects are grouped by lifecycle stage for clarity and code quality:

* **archive** — inactive or abandoned code kept temporarily for reference
* **draft** — experimental or incomplete work in progress
* **project** — stable, actively developed, and reliable code

This separation keeps mature work distinct from experiments and enables deliberate cleanup of obsolete ideas.

---

### GitHub approach (current state only)

GitHub contains only **active projects**:

* Each repository represents the **current valid version** of a project concept
* Repo names stay clean and stable (e.g. `repo-name`)
* If a project is rethought, the existing repo is **deleted**
* A new repo is created under the same name when needed

GitHub reflects only the current working state, not history.

---

### Local workspace organization

Locally, all work is preserved by lifecycle stage:

* `~/code/project/` — active development
* `~/code/draft/` — experimental or rewritten work
* `~/code/archive/` — abandoned or failed implementations (temporary before deletion)

This preserves learning from all attempts while keeping GitHub minimal.

---

### Core principle

> GitHub = current truth
> Local workspace = full history (including experiments and failures)