<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
<!-- diskwise-meta: {"last_verified":"2026-02-20T05:20:36Z","verify_count":1,"fail_count":0} -->
# Cabal

Cabal is the Haskell build tool and package manager.

## Where it stores data

- `~/.cabal/store/` — compiled package database (the global store)
- `~/.local/state/cabal/` — newer cabal state directory
- `~/.cabal/packages/` — downloaded package index
- `~/.cabal/logs/` — build logs
- `dist-newstyle/` — per-project build artifacts (in project root)

## What's safe to delete

- `dist-newstyle/` — per-project build cache, rebuilt on next `cabal build`
- `~/.cabal/logs/` — build log files
- `~/.cabal/packages/hackage.haskell.org/01-index.tar` — package index cache (re-downloaded on `cabal update`)
- Old entries in `~/.cabal/store/` for GHC versions you no longer have installed

## What's NOT safe to delete

- `~/.cabal/store/` entries for your active GHC version — deleting these forces full rebuilds of all dependencies
- `~/.cabal/config` — your cabal configuration

## Cleanup commands

```bash
# Remove project build artifacts
rm -rf dist-newstyle/

# Remove build logs
rm -rf ~/.cabal/logs/*

# Remove store entries for a specific GHC version you no longer use
rm -rf ~/.cabal/store/ghc-9.4.7/

# Nuclear option: clear entire store (forces full rebuilds)
rm -rf ~/.cabal/store/
```

## Typical space usage

- `~/.cabal/store/`: 2-10 GB per GHC version depending on packages
- `dist-newstyle/`: 500 MB - 3 GB per project
- Package index: ~200 MB

## Platform notes

- On newer cabal versions (3.10+), state moves to `~/.local/state/cabal/`
- The `dist-newstyle` directory contains platform-specific build artifacts and is not portable

## History

- 2026-02-20: Initial page (seed)
