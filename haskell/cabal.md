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


# Cabal (Haskell build tool)

Cabal is the Haskell package manager and build system.

## Where it stores data
- `~/PortableHaskell/cabal/packages/hackage.haskell.org/` — package index and downloaded packages
- `~/PortableHaskell/cabal/logs/` — build logs
- `~/PortableHaskell/cabal/store/` — compiled package store

## What's safe to delete
- **Build logs** (`cabal/logs/`): ~5 MB typical (observed on this system, 2026-02-20). Low risk.

## What's NOT safe to delete
- **Package index cache** (`01-index.tar`, `01-index.tar.gz`): ~1.1 GB combined (observed on this system, 2026-02-20). Deleting this forces a full re-download of ~956 MB on next `cabal update`. A previous cleanup session deleted this and the user reported having to re-download 956 MB. **Do not recommend deleting this unless the user explicitly asks.** The re-download cost far outweighs the space savings.

## Cleanup commands
```bash
# Safe: clear build logs only
rm -rf ~/PortableHaskell/cabal/logs/*
```

## Typical space usage
- Package index: ~1.1 GB (observed on this system, 2026-02-20)
- Build logs: ~5 MB (observed on this system, 2026-02-20)

## Platform notes
- On mingw64_nt-10.0-17763 (x86_64): Cabal installed via ghcup under `~/PortableHaskell/cabal/` rather than the default `~/.cabal/` path.

## History
- 2026-02-20: Created page. Documented that deleting package index cache caused 956 MB re-download — marked as NOT safe to delete. Build logs ~5 MB confirmed. (agent@Win-APP)