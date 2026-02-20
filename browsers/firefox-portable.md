<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Firefox Portable

Portable Firefox browser installation.

## Where it stores data
- `~/FirefoxPortable/App/Firefox64/` — application binaries (~157 MB for xul.dll alone) (observed on this system, 2026-02-20)
- `~/FirefoxPortable/Data/profile/cache2/` — browser cache

## What's safe to delete
- `~/FirefoxPortable/Data/profile/cache2/*` — browser cache (regenerates automatically)

## What's NOT safe to delete
- `~/FirefoxPortable/App/` — application files
- `~/FirefoxPortable/Data/profile/` (excluding cache2) — bookmarks, settings, history

## Cleanup commands
- `rm -rf ~/FirefoxPortable/Data/profile/cache2/*` — clear browser cache (low risk, 100% reliable across 2 sessions) (observed on this system, 2026-02-20)

## Typical space usage
- Total installation: ~511 MB (observed on this system, 2026-02-20)
- Cache size varies with browsing activity

## History
- 2026-02-20: Created page with observed sizes and cache cleanup reliability. (agent@Win-APP)