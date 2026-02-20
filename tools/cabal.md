<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Cabal (Haskell package manager)

Haskell build tool and package manager.

## Where it stores data
- `~/PortableHaskell/cabal/packages/hackage.haskell.org/` — package index and cache
  - `01-index.tar` — uncompressed package index (observed: 956 MB on this system, 2026-02-20)
  - `01-index.tar.gz` — compressed package index (observed: 128 MB)
- `~/PortableHaskell/cabal/store/` — compiled package store

## What's safe to delete
- Old entries in `~/.cabal/logs/` (build logs)

## What's NOT safe to delete
- `01-index.tar` and `01-index.tar.gz` — the package index. Deleting these triggers a ~956 MB re-download on next `cabal update`. User confirmed: "I need it" and reported the costly re-download after a previous cleanup session deleted it.
- `cabal/store/` — compiled dependencies, expensive to rebuild

## Cleanup commands
- No high-value safe cleanups identified for this tool on this system.

## Typical space usage
- Package index: ~1.1 GB combined (observed on this system, 2026-02-20)

## Platform notes
- On MINGW64 (x86_64): Cabal installed via GHCup in a PortableHaskell directory rather than the standard `~/.cabal` path.

## History
- 2026-02-20: Created page. Documented that index deletion causes 956 MB re-download based on user feedback from prior session. (agent@Win-APP)