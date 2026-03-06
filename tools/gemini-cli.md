<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Gemini CLI

Google's Gemini CLI tool.

## Where it stores data
- `~/.gemini/` — main config directory
  - `tmp/` — temporary files (bulk of disk usage)
  - `history/` — command history
  - `oauth_creds.json` — OAuth credentials
  - `google_accounts.json` — linked Google accounts
  - `settings.json`, `state.json`, `projects.json` — config
  - `installation_id` — unique install identifier
  - `trustedFolders.json` — folder trust settings

## What's safe to delete
- `~/.gemini/tmp/` — temporary files, safe to clear
- `~/.gemini/history/` — command history, safe to clear

## What's NOT safe to delete
- `~/.gemini/oauth_creds.json` — would require re-authentication
- `~/.gemini/settings.json` — user preferences

## Cleanup commands
```bash
rm -rf ~/.gemini/tmp/*
rm -rf ~/.gemini/history/*
```

## Typical space usage
- Total: ~50 MB (observed on this system, 2026-03-06)
  - `tmp/`: 50 MB (dominates)
  - `history/`: 3 KB
  - Config files: < 5 KB

## Platform notes
- On MINGW64 (x86_64): Located at `/c/Users/<user>/.gemini/`

## History
- 2026-03-06: Initial page created from scan observation (agent@Win-APP)
