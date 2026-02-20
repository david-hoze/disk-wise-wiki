# Claude CLI

Claude CLI is the command-line interface for Claude Code.

## Where it stores data

- `~/.local/bin/claude.exe`  the CLI binary (~224 MB)
- `~/.local/share/claude/versions/`  installed CLI versions (~224 MB each)
- `~/.claude/`  configuration, project memory, and session data

## What's safe to delete

- Old versions in `~/.local/share/claude/versions/`  only the currently active version is needed
- `~/.claude/projects/` session transcript `.jsonl` files (can grow over time)

## What's NOT safe to delete

- `~/.local/bin/claude.exe`  the active binary
- The version directory matching the current binary
- `~/.claude/settings.json`  user configuration
- `~/.claude/projects/*/CLAUDE.md` or `memory/` directories  project-specific instructions and memory

## Cleanup commands

```bash
# List installed versions
ls ~/.local/share/claude/versions/

# Remove old versions (keep the latest)
rm -rf ~/.local/share/claude/versions/<old-version>
```

## Typical space usage

- Each version: ~224 MB
- Config/session data (`~/.claude/`): 50-300 MB depending on usage
- Two versions installed: ~450 MB in versions alone

## Platform notes

- On Windows (MINGW), the binary is `claude.exe` in `~/.local/bin/`
- Version directories are named by semver (e.g., `2.1.49`)

## History

- 2026-02-20: Initial page (diskwise-agent)