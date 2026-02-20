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


# Cabal (Haskell Package Manager)

Haskell build tool and package manager. On portable setups, lives under `~/PortableHaskell/cabal/`.

## Where it stores data
- `~/PortableHaskell/cabal/packages/hackage.haskell.org/01-index.tar` — package index (~956 MB) (observed on this system, 2026-02-20)
- `~/PortableHaskell/cabal/packages/hackage.haskell.org/01-index.tar.gz` — compressed package index (~128 MB) (observed on this system, 2026-02-20)
- `~/PortableHaskell/cabal/store/` — compiled package store
- `~/PortableHaskell/cabal/logs/` — build logs

## What's safe to delete
- Build logs under `~/PortableHaskell/cabal/logs/`
- Stale entries in `~/PortableHaskell/cabal/store/` (use caution)

## What's NOT safe to delete
- **`~/PortableHaskell/cabal/packages/` (package index)** — Re-downloading costs ~956 MB of bandwidth and significant time. User reported this as a painful mistake after a previous cleanup session deleted it. Do NOT suggest deleting this.
- `~/PortableHaskell/cabal/config` — configuration file

## Cleanup commands
- `rm -rf ~/PortableHaskell/cabal/logs/*` — remove build logs (low risk)
- Per-project: `cabal clean` in project directories removes `dist-newstyle/`

## Typical space usage
- Package index: ~1.1 GB total (tar + tar.gz) (observed on this system, 2026-02-20)
- Full cabal directory varies by number of installed packages

## Platform notes
- On mingw64_nt-10.0-17763 (x86_64): Portable Haskell installs use `~/PortableHaskell/cabal/` instead of the standard `~/.cabal/` or `~/AppData/Roaming/cabal/`.

## History
- 2026-02-20: Created page. Documented package index as NOT safe to delete based on user feedback reporting 956MB re-download after deletion. (agent@Win-APP)