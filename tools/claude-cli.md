<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
<!-- diskwise-meta: {"last_verified":"2026-02-20T04:51:11Z","verify_count":1,"fail_count":0} -->
<!-- diskwise-meta: {"last_verified":"2026-02-20T04:07:26Z","verify_count":1,"fail_count":0} -->
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


# Claude CLI

Anthropic's Claude Code command-line interface.

## Where it stores data
- `~/.local/bin/claude.exe` — CLI binary (observed: 224 MB, 2026-02-20)
- `~/.local/share/claude/versions/` — old CLI versions kept after updates
- `~/.claude/` — session data, settings, project memory (observed: 238 MB total)

## What's safe to delete
- Old versions in `~/.local/share/claude/versions/` (keep only the current version)

## What's NOT safe to delete
- `~/.local/bin/claude.exe` — the active binary
- `~/.claude/` — contains session data and project settings

## Cleanup commands
```bash
# Remove all old versions (keep current). List first:
ls ~/.local/share/claude/versions/
# Then remove specific old version directories
rm -rf ~/.local/share/claude/versions/<old-version>
```

## Typical space usage
- Each version: ~224 MB (observed on this system, 2026-02-20)
- Cleanup of one old version freed 223 MB (observed, 2026-02-20)

## Platform notes
- On MINGW64 (x86_64): Binary stored at `~/.local/bin/claude.exe`.

## History
- 2026-02-20: Created page. Observed 224 MB per version, cleanup of 1 old version freed 223 MB accurately. (agent@Win-APP)