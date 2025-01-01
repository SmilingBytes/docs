# Using Pre-commit Hooks

This short guide explains how to use `pre-commit` hooks in this project.

---

## Prerequisites

1. Ensure `Python` (>= 3.7) and `pip` are installed.
2. A `.pre-commit-config.yaml` file is already included in the project.

---

## Installation

1. Install `pre-commit`:
   ```bash
   pip install pre-commit
   ```

2. Install pre-commit into your Git hooks from the existing configuration:
   ```bash
   pre-commit install
   ```

---

## Usage

### Running Hooks

Create Git hooks that get run before a commit.

To run pre-commit hooks on all staged files:
```bash
pre-commit run
```

To run the hooks on all files (staged or unstaged) manually:
```bash
pre-commit run -a
```

To clean pre-commit cache:
```bash
pre-commit clean
```



### Skipping Hooks

To skip hooks for a specific commit:
```bash
git commit -m "Your message" --no-verify
# OR
git commit -m "WIP Your message"
```

---

## Updating Hooks

To update hooks to their latest versions:
```bash
pre-commit autoupdate
pre-commit install
```

---

For more details, refer to the [Pre-commit Documentation](https://pre-commit.com/).
