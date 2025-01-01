# Using Poetry in This Project

This guide provides a quick overview of using Poetry for dependency management and packaging in Python projects.

---

## What is Poetry?

Poetry is a Python dependency management and packaging tool. It handles dependency resolution, environment management, and package publishing through a `pyproject.toml` file.

---

## Prerequisites

1. Install Poetry:
   ```bash
   curl -sSL https://install.python-poetry.org | python3 -
   ```
   Or, if using Arch Linux:
   ```bash
   sudo pacman -S poetry
   ```

2. Verify the installation:
   ```bash
   poetry --version
   ```

---

## Basic Commands

### Adding a New Package

To add a package with a specific version:
```bash
poetry add package-name==x.y.z
```

To allow minor version updates (e.g., `^1.2.3` allows updates to `1.x.x`):
```bash
poetry add package-name@^1.2.3
```

To allow patch version updates (e.g., `~1.2.3` allows updates to `1.2.x`):
```bash
poetry add package-name@~1.2.3
```

To add a package from a specific git repository:
```bash
poetry add git+https://github.com/user/repo.git#develop
# OR
poetry add git+ssh://git@github.com:user/repo.git#develop
```

To add a development dependency:
```bash
poetry add --dev package-name
```

### Removing a Package

To remove a package:
```bash
poetry remove package-name
```

### Updating a Package

To update a package:
```bash
poetry update package-name
```

To update a package to the latest version:
```bash
poetry add package-name@latest
```

To update all packages:
```bash
poetry update
```

---

## Managing the Virtual Environment

To install dependencies specified in `pyproject.toml`:
```bash
poetry install
```

To activate Poetry's virtual environment:
```bash
poetry shell
```

To run a command in the virtual environment without activating it:
```bash
poetry run python backend/main.py
```

---

## Exporting Requirements

### Export Main Dependencies

To export only the main dependencies to a `requirements.txt` file:
```bash
poetry export --format=requirements.txt --without-hashes --without-urls --verbose --only main | sed 's/ ; python_version .*//' > requirements.txt
```

### Export Development Dependencies

To export only the development dependencies to a `requirements-dev.txt` file:
```bash
poetry export --format=requirements.txt --without-hashes --without-urls --verbose --only dev | sed 's/ ; python_version .*//' > requirements-dev.txt
```

---


## Trace / Show

To list all the available packages:
```bash
poetry show
```
Available options:
```bash
    --with: The optional dependency groups to include (dev).
    --without: The dependency groups to ignore.
    --why: When showing the full list, or a --tree for a single package, display whether they are a direct dependency or required by other packages.
    --only: The only dependency groups to include (main or dev).
    --tree: List the dependencies as a tree.
    --latest (-l): Show the latest version.
    --outdated (-o): Show the latest version but only for packages that are outdated.
    --all (-a): Show all packages (even those not compatible with current system).
    --top-level (-T): Only show explicitly defined packages.
```

---

## Additional Resources

- [Poetry Documentation](https://python-poetry.org/docs/)
- [PEP 621: pyproject.toml](https://peps.python.org/pep-0621/)

---

Poetry simplifies dependency management and ensures consistency across environments. Happy coding!
