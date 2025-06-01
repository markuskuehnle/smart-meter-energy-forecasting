# Smart Meter - Energy Forecasting

---

## Development Setup 

Setup is done with astral uv
https://docs.astral.sh/uv/

### Setup virtual environment with UV

```bash
uv venv .venv
```

activate your venv, then continue with the next step

### Install Pre-Commit Hooks

on CLI run:

```bash
pre-commit install
pre-commit run --all-files
```

# Short note on commit messages

It would be great if we could use **conventional commit** messages

Documentation: https://www.conventionalcommits.org/en/v1.0.0/

**Use only these 5 commit types for easier traceability of our commit history:**

Examples:

- adding a new feature:

```
feat: allow provided config object to extend other configs
```

- fixing a bug:

```
fix: prevent racing of requests
```

- changing something without code / function changes

```
chore: update README
```

- commit message with no body (no file content was changes → renames, deletions)

```
docs: correct spelling of CHANGELOG
```

- refactor code

```
refactor: clean up data preprocessing logic
```

No scope specification needed