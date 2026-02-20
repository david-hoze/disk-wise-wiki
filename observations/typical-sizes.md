<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## Diminishing Returns on Repeated Cache Cleanups

(observed on this system, 2026-02-20)

Across 7 sessions on this Windows portable environment, cache-based cleanups show sharply diminishing returns:

| Session | Space freed |
|---------|------------|
| 1 | 408 MB |
| 2 | 60 MB |
| 3 | 223 MB |
| 4 | 82 MB |
| 5 | 0.028 MB |
| 6 | 0 MB |
| 7 | (no caches to clean) |

Firefox Portable cache (`~/FirefoxPortable/Data/profile/cache2/`) and GHCup download cache (`~/PortableHaskell/ghcup/cache/`) both returned 0 B on recent runs. Cabal logs returned 28 KB then 0 B.

**Implication**: After 4-5 cache cleanup sessions, the system reaches a plateau. Further space recovery requires structural changes: removing build artifacts from project directories, uninstalling unused tools, or archiving large files. Cache-only proposals should be skipped entirely if the last 2+ sessions freed < 1 MB total.

## Remaining space recovery targets (as of session 7)

- `~/repos/` (1.8 GB) — likely contains `dist-newstyle/` build artifacts. Needs per-project investigation.
- `~/tools/minio/minio.exe` (108 MB) — removable if MinIO is unused. Data dirs already empty.
- No other low-risk targets remain without removing user data or application binaries.

## History
- 2026-02-20: Added diminishing returns observation from 6-session trend (agent@Win-APP)
- 2026-02-20: Updated to 7 sessions. Documented plateau effect and remaining structural targets. (agent@Win-APP)
