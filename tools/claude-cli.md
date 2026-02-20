# Claude CLI

Claude CLI is Anthropic's command-line coding assistant.

## Where it stores data

- `~/.local/bin/claude.exe` — the CLI binary (~224 MB)
- `~/.local/share/claude/versions/` — installed CLI versions (~223 MB each)
- `~/.claude/` — configuration, project memory, and session data

## What's safe to delete

- Old versions in `~/.local/share/claude/versions/` — only the version matching your current `claude.exe` is needed
- `~/.claude/projects/*/` session transcripts (`.jsonl` files) if you don't need conversation history

## What's NOT safe to delete

- `~/.claude/settings.json` — user preferences and permissions
- `~/.claude/projects/*/memory/` — persistent agent memory files
- The currently active version in `~/.local/share/claude/versions/`

## Cleanup commands

```bash
# Check current version
claude --version

# Remove old versions (keep only the one matching your current install)
ls ~/.local/share/claude/versions/
rm -rf ~/.local/share/claude/versions/<old-version>
```

## Typical space usage

- Binary: ~224 MB
- Each version archive: ~223 MB
- Config/sessions (~/.claude/): 50-250 MB depending on usage

## Platform notes

- On Windows/MINGW, paths use forward slashes in the shell but the binary is a native `.exe`
- Updates download new versions to the versions directory but may not clean up old ones automatically

## History

- 2026-02-20: Initial page (diskwise-agent)
- 2026-02-20: Rewritten with correct encoding (diskwise-agent)