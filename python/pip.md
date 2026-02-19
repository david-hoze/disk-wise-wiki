# pip

pip is the standard Python package installer.

## Where it stores data

- `~/.cache/pip/` — downloaded package cache
- `~/.cache/pip/wheels/` — built wheel cache
- `~/.local/lib/python*/` — user-installed packages

## What's safe to delete

- `~/.cache/pip/` — entire cache directory, re-downloaded as needed
- Old virtual environments (`venv/`, `.venv/`, `env/`) for inactive projects

## What's NOT safe to delete

- `~/.local/lib/python*/` — user-installed packages you're actively using
- Active virtual environments

## Cleanup commands

```bash
# Clear pip cache
pip cache purge

# Check cache size
pip cache info

# Remove a specific package's cache
pip cache remove <package>
```

## Typical space usage

- `~/.cache/pip/`: 200 MB - 2 GB
- Virtual environments: 100 MB - 1 GB each

## History

- 2026-02-20: Initial page (seed)
