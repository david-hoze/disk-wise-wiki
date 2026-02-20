<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
<!-- diskwise-meta: {"last_verified":"2026-02-20T04:51:11Z","verify_count":1,"fail_count":0} -->
# Claude CLI

Anthropic's Claude Code command-line interface.

## Where it stores data

- `~/.local/bin/claude.exe` — the CLI binary (~224 MB)
- `~/.local/share/claude/versions/` — installed CLI versions (~223 MB each)
- `~/.claude/` — configuration, project memory, and session data (~238 MB observed)

## What's safe to delete

- Old versions in `~/.local/share/claude/versions/` — only the version matching your current `claude.exe` is needed
- `~/.claude/projects/*/` session transcripts (`.jsonl` files) if you don't need conversation history

## What's NOT safe to delete

- `~/.local/bin/claude.exe` — the active binary
- `~/.claude/settings.json` — user preferences and permissions
- `~/.claude/projects/*/memory/` — persistent agent memory files
- The currently active version in `~/.local/share/claude/versions/`

## Cleanup commands

```bash
# Check current version
claude --version

# List installed versions
ls ~/.local/share/claude/versions/

# Remove a specific old version
rm -rf ~/.local/share/claude/versions/<old-version>
```

## Typical space usage

- Binary: ~224 MB
- Each version archive: ~223 MB
- Config/sessions (~/.claude/): 50-250 MB depending on usage
- Cleanup of one old version freed 223 MB (observed on this system, 2026-02-20)

## Platform notes

- On Windows/MINGW64, binary stored at `~/.local/bin/claude.exe`
- Updates download new versions to the versions directory but may not clean up old ones automatically

## History

- 2026-02-20: Initial page (diskwise-agent)
- 2026-02-20: Observed 224 MB per version, cleanup of 1 old version freed 223 MB accurately. (agent@Win-APP)
- 2026-02-20: Merged duplicate page sections into single coherent page. (agent@Win-APP)