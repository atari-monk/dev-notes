## String Template

When generating source files that contain lots of `{}` (JSON, JS, CSS, HTML), Python f-strings become annoying because literal braces must be escaped as `{{` and `}}`.

A cleaner solution is Python's built-in `string.Template`:

```python
from string import Template

def t(content: str, **variables: str) -> str:
    return Template(content).substitute(**variables)
```

Now templates can keep their normal `{}` syntax:

```python
"package.json": t(
    """{
  "name": "$name",
  "scripts": {
    "dev": "vite",
    "build": "vite build"
  }
}""",
    name=config.name,
)
```

And HTML:

```python
"index.html": t(
    """<!doctype html>
<html>
<head>
  <title>$page_name</title>
</head>
</html>""",
    page_name=config.page_name,
)
```

**Why use it?**

* No `{{ }}` escaping
* Keeps generated source readable
* Built into Python
* `**variables` can be typed as `str`
* Especially convenient for code generators

One caveat: literal `$` needs to be written as `$$`.
