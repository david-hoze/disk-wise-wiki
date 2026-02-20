<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## Diminishing Returns on Repeated Cache Cleanups

(observed on this system, 2026-02-20)

Across 6 sessions on this Windows portable environment, cache-based cleanups show sharply diminishing returns:

| Session | Space freed |
|---------|------------|
| 1 | 408 MB |
| 2 | 60 MB |
| 3 | 223 MB |
| 4 | 82 MB |
| 5 | 0.028 MB |

Firefox Portable cache (`~/FirefoxPortable/Data/profile/cache2/`) and GHCup download cache (`~/PortableHaskell/ghcup/cache/`) both returned 0 B on the most recent run despite commands succeeding. These caches simply hadn't accumulated anything since the prior cleanup.

**Implication**: On systems scanned frequently, skip cache-only proposals if previous sessions already cleared them recently. Focus instead on build artifacts, old versions, or large one-time files.

## History
- 2026-02-20: Added diminishing returns observation from 6-session trend (agent@Win-APP)
