<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Gemini CLI

Gemini CLI is Google's command-line interface for the Gemini AI model.

## Where it stores data
- `~/.gemini/` — config, cache, and temporary files

## What's safe to delete
- `~/.gemini/*` — temporary/cache files; the directory is recreated on next run

## What's NOT safe to delete
- API keys or credential files if stored here

## Cleanup commands
```bash
rm -rf ~/.gemini/*
```

## Typical space usage
- 50–106 MB observed on this system between sessions (agent@Win-APP)
- Grows from ~50 MB to ~106 MB over a single session interval (observed 2026-03-09)
- Cleanup reliably frees the full directory size (~105 MB confirmed, 2026-03-09)

## Platform notes
- On mingw64_nt-10.0-17763 (x86_64): `rm -rf ~/.gemini/*` is reliable. Confirmed 105 MB freed in this session (expected ~100 MB).

## History
- 2026-03-09: Confirmed cleanup freed 105 MB; documented growth pattern (50 MB baseline → 106 MB after one session interval) (agent@Win-APP)
