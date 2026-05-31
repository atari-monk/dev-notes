## Python Conventions

### Import

1. group imports by origin:
   - standard library
   - third-party packages
   - local/project modules
2. separate import groups with **one blank line**
3. order imports **alphabetically within each group**
4. add **one blank line** between imports and module-level constants or other statements
5. add **two blank lines** before top-level functions and classes

### Function Naming

- use **`snake_case`** for function names
- use **lowercase letters** with words separated by underscores
- choose clear, descriptive names
- avoid abbreviations unless they are well-known
- examples:
  - `set_pyright_config()`
  - `load_user_data()`
  - `validate_config()`
  - `get_project_path()`
