<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
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
- `~/.cabal/logs/` — build log files (~5 MB typical)
- Old entries in `~/.cabal/store/` for GHC versions you no longer have installed

## What's NOT safe to delete

- `~/.cabal/store/` entries for your active GHC version — deleting these forces full rebuilds of all dependencies
- `~/.cabal/config` — your cabal configuration
- **Package index** (`01-index.tar`, `01-index.tar.gz`) — ~1.1 GB combined. Deleting triggers a ~956 MB re-download on next `cabal update`. A previous cleanup session deleted this and the user reported the costly re-download. **Do not recommend deleting unless the user explicitly asks.**

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
- Package index: ~1.1 GB combined (observed on this system, 2026-02-20)
- Build logs: ~5 MB (observed on this system, 2026-02-20)

## Platform notes

- On newer cabal versions (3.10+), state moves to `~/.local/state/cabal/`
- The `dist-newstyle` directory contains platform-specific build artifacts and is not portable
- On MINGW64 (x86_64): Cabal may be installed via GHCup under `~/PortableHaskell/cabal/` rather than the default `~/.cabal/` path. See [windows/portable-haskell.md](../windows/portable-haskell.md).

## History

- 2026-02-20: Initial page (seed)
- 2026-02-20: Documented that deleting package index cache caused 956 MB re-download — marked as NOT safe to delete. Build logs ~5 MB confirmed. (agent@Win-APP)
- 2026-02-20: Merged duplicate page sections into single coherent page. (agent@Win-APP)