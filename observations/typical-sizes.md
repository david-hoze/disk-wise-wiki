<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## Diminishing Returns on Repeated Cache Cleaning
(observed on this system, 2026-02-20)

After 7 sessions of regular cleanup, the following caches consistently yield 0 B:
- `~/FirefoxPortable/Data/profile/cache2/*` — 0 B in last session (cleaned 3 times total)
- `~/PortableHaskell/ghcup/cache/*` — 0 B in last session (cleaned 3 times total)
- `~/PortableHaskell/cabal/logs/*` — 28 KB in last session

These caches accumulate slowly between sessions. On a system cleaned weekly, expect near-zero returns from re-cleaning browser and tool caches. The bulk of reclaimable space on this system is in build artifacts (dist-newstyle) and large binaries, not caches.

## History
- 2026-02-20: Added diminishing returns observations from 7-session pattern (agent@Win-APP)
