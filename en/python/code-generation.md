## A Few Python Tools That Make Code Generation Cleaner

When writing a small Python tool that generates project files, a few standard-library features make the code considerably cleaner.

### `Path` for files

Instead of passing around raw strings for file paths, `pathlib.Path` gives us a proper path object:

```python
from pathlib import Path

source = Path("template/main.ts")
destination = Path("dist/main.ts")
```

It also makes validation straightforward:

```python
if not source.is_file():
    logger.warning("Source file does not exist: %s", source)
    return
```

### `shutil` for copying

For the actual file operation, `shutil.copy2()` is a convenient choice:

```python
shutil.copy2(source, destination)
```

It copies the file while attempting to preserve its metadata.

When generating files, it's also a good idea not to silently overwrite existing work:

```python
if destination.exists():
    logger.warning("Destination already exists: %s", destination)
    return
```

### `Logger` instead of `print`

Passing a `Logger` into the function keeps the file operation independent of how logging is configured:

```python
def copy_file_with_logging(
    source: Path,
    destination: Path,
    logger: Logger,
) -> None:
    ...
```

The function can simply report what happened:

```python
logger.info("Copied %s to %s", source, destination)
```

{% raw %}

### F-strings vs `Template`

Python f-strings are great when inserting a few Python values:

```python
return f"""
base: '/pages/{config.name}/'
"""
```

But there's a catch when generating JavaScript or TypeScript: those languages use `{}` everywhere.

An f-string therefore forces us to escape literal braces:

```python
f"""
import {{ defineConfig }} from 'vite'

export default defineConfig({{

    base: '/pages/{config.name}/',

}})
"""
```

For larger code templates, `string.Template` can be more pleasant:

```python
from string import Template

return Template("""
import { defineConfig } from 'vite'

export default defineConfig({

    base: '/pages/$name/',

})
""").substitute(name=config.name)
```

Now JavaScript's `{}` remain untouched, and only `$name` is interpreted by Python.

### Multiple substitutions

`substitute()` accepts multiple values in one call:

```python
Template("""
name: $name
version: $version
path: $path
""").substitute(
    name=config.name,
    version=config.version,
    path=config.path,
)
```

You generally want one substitution call rather than chaining them, because `substitute()` returns a regular `str`.

{% endraw %}

### The rule of thumb

For this kind of project generator:

- **`Path`** → file paths and filesystem checks
- **`shutil`** → copying files
- **`Logger`** → reporting operations and failures
- **f-strings** → small strings with interpolation
- **`Template`** → larger source-code templates containing lots of `{}`

The main lesson is that Python's standard library already gives us most of the building blocks needed for a clean little project generator—without having to invent abstractions around basic filesystem and templating tasks.
