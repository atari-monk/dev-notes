## Custom Title

### Contents
- [Overview](#overview)
- [How it works](#how-it-works)
- [Configuration](#configuration)
- [Notes](#notes)

---

### Overview

In GitHub Pages, the default site title is often taken from the repository name. This can be overridden to display a custom title in the page header.

[Contents](#contents)

---

### How it works

Most GitHub Pages sites (especially those using Jekyll) render the title from the `site.title` variable. If it is not defined, the system falls back to the repository name.

[Contents](#contents)

---

### Configuration

To set a custom title, define it in the `_config.yml` file:

```yml
title: Tech Notes
description: Personal collection of technical notes
````

This will replace the default repository-based title in the site header.

[Contents](#contents)

---

### Notes

* Works with most Jekyll-based GitHub Pages themes
* Some themes may override layout behavior
* Changes require redeploy (push to GitHub)

[Contents](#contents)

---
