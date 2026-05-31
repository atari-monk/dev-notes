## Python Commands

### Virtual environment

```bash
# 1. Create virtual environment
python3 -m venv .venv

# 2. Activate it
source .venv/bin/activate
```

**Note:** In VS Code, select `.venv/bin/python` via **Python: Select Interpreter**.

### Install pytest

```bash
# 1. Upgrade pip
python -m pip install --upgrade pip

# 2. Install pytest
python -m pip install pytest

# 3. Verify installation
python -m pytest --version
```

### Run tests

```bash
# 1. Activate virtual environment
source .venv/bin/activate

# 2. Install the project in editable mode
python -m pip install -e .

# 3. Run all tests and stop at the first failure
python -m pytest -x
```

**Note:** `-x` stops pytest after the first failed test. If all tests pass, pytest runs the entire test suite.
