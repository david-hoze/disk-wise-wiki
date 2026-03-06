<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## Directory Size Breakdown
(observed on this system, 2026-03-06)

Total: 775 MB
- `~/.claude/projects/` — 545 MB (session transcripts, memory files)
- `~/.claude/debug/` — 180 MB (debug logs)
- `~/.claude/file-history/` — 36 MB
- `~/.claude/plugins/` — 6 MB
- `~/.claude/telemetry/` — 3.8 MB
- `~/.claude/shell-snapshots/` — 2.3 MB
- `~/.claude/paste-cache/` — 844 KB
- Other dirs — <1 MB each

## What's safe to delete
- `~/.claude/debug/` — debug logs, ~180 MB. Regenerated as needed.
- `~/.claude/paste-cache/` — temporary paste data

## What's NOT safe to delete
- `~/.claude/projects/` — contains memory files and session data
- `~/.claude/plugins/` — installed MCP plugins

## History
- 2026-03-06: Added directory size breakdown from scan (agent@Win-APP)
