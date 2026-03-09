<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Claude CLI

Claude CLI (`claude`) is Anthropic's command-line interface for Claude.

## Where it stores data
- `~/.local/bin/claude.exe` — active symlink/binary (~230 MB)
- `~/.local/share/claude/versions/` — versioned installs; old versions persist after upgrades
- `~/.claude/` — configuration, conversation history, debug logs
  - `~/.claude/debug/` — debug log files; can grow substantially between sessions

## What's safe to delete
- Old versions in `~/.local/share/claude/versions/<old-version>/` once a newer version is active
- `~/.claude/debug/*` — debug logs; regenerated on next run

## What's NOT safe to delete
- The currently active version directory (matches the symlinked binary size)
- `~/.claude/` conversation history if you want to keep past context

## Cleanup commands
```bash
# Remove a specific old version (replace 2.1.70 with the old version)
rm -rf ~/.local/share/claude/versions/2.1.70

# Clear debug logs
rm -rf ~/.claude/debug/*
```

## Typical space usage
- Each version: ~230–240 MB
- Debug logs: 0–201 MB per session interval; grows unpredictably (observed on this system, 2026-03-09)
  - Was 0 B in one session, 180 MB in another, 201 MB in this session
  - The 0–180 MB estimate understates the upper bound; treat as 0–210 MB

## Platform notes
- On mingw64_nt-10.0-17763 (x86_64): versions are stored as directories under `~/.local/share/claude/versions/`, each ~230 MB. Old versions are not auto-removed on upgrade.

## History
- 2026-03-09: Documented versions directory cleanup; updated debug log size range to 0–210 MB based on observed 201 MB (exceeded prior 0–180 MB estimate); confirmed rm of debug/* is reliable (agent@Win-APP)
