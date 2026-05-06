## No Jekyll

[pl](pl/no-jekyll.md)

Disabling Jekyll in GitHub Pages mean that **GitHub Pages will stop automatically converting Markdown to HTML**.

### What happens after disabling Jekyll?

If you add a `.nojekyll` file to your repository:

* GitHub Pages **does not run Jekyll**
* **Markdown (`.md`) is no longer automatically rendered into HTML**
* files are served “as-is” from the repository

So:

* `index.html` → works normally
* `notes.md` → will be downloaded as a text file or shown as raw text (depending on the browser), but **not as a webpage**

---

## Do you have to write in HTML then?

**No, but you have 3 options:**

### 1. ✔️ Markdown + your own build (most common solution)

You keep writing in `.md`, but:

* you use **GitHub Actions**
* with a generator like:

  * Hugo
  * MkDocs
  * Astro
  * Eleventy
  * Docusaurus

These:

* convert Markdown → HTML
* publish the ready site to `gh-pages` or `/docs`

👉 This gives full control and avoids Jekyll.

---

### 2. ✔️ Markdown + Jekyll (default GitHub Pages)

If you do NOT add `.nojekyll`, GitHub:

* automatically renders Markdown → HTML
* uses Jekyll

This is the simplest option, but less flexible.

---

### 3. ✔️ Static HTML (no conversion)

You can:

* write HTML manually
* or generate it locally

Pros:

* full control

Cons:

* less convenient than Markdown

---

## Key summary

| Option                              | Markdown works | Auto conversion | Convenience |
| ----------------------------------- | -------------- | --------------- | ----------- |
| Jekyll (default)                    | ✔️             | ✔️              | high        |
| `.nojekyll` + no build              | ❌              | ❌               | low         |
| `.nojekyll` + CI (Hugo/MkDocs etc.) | ✔️             | ✔️ (in CI)      | very high   |
| pure HTML                           | ❌              | ❌               | medium      |

---

## Conclusion

If you want:

> “full control over your notes”

then the best setup is:
👉 **Markdown + GitHub Actions + a generator (e.g. MkDocs or Hugo)**
not writing HTML manually.

---

If you want, I can suggest a specific setup (e.g. a minimal “Obsidian-like notes + GitHub Pages” workflow).
