<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# GHCup

GHCup is the Haskell toolchain manager for GHC, Cabal, HLS, and Stack.

## Where it stores data
- `~/.ghcup/` — standard install location (Linux/macOS)
- `~/PortableHaskell/ghcup/` — Portable Haskell variant on Windows (observed on this system)
  - `ghc/` — installed GHC versions
  - `bin/` — HLS binaries and other tool executables (observed on this system, 2026-03-09)
  - `cache/` — download cache
  - `logs/` — installation logs

## What's safe to delete
- `ghcup/cache/*` — download cache, regenerated on demand (100% reliable across 4 sessions)
- Old GHC versions not set as current: `ghcup rm ghc <version>`
- Old HLS versions not needed: `ghcup rm hls <version>`

## What's NOT safe to delete
- The currently active GHC version (marked `IS` in `ghcup list`)
- The currently active HLS version
- `ghcup/ghc/<active-version>/` — deleting this breaks compilation

## Cleanup commands
```bash
# Remove download cache (safe, always re-downloadable)
rm -rf ~/PortableHaskell/ghcup/cache/*

# List installed versions with their status
ghcup list

# Remove a specific unused GHC version
ghcup rm ghc 9.4.7

# Remove a specific unused HLS version
ghcup rm hls 2.12.0.0
```

## Typical space usage
- GHC 9.6.7 install: 3.1 GB (observed on this system, 2026-03-09)
- HLS 2.13.0.0 binaries: ~500 MB total across `ghcup/bin/` (two files: wrapper + server)
- ghcup cache: 0–200 MB depending on recent activity

## Platform notes
- On mingw64_nt-10.0-17763 (x86_64) with Portable Haskell: HLS is stored as flat executables in `~/PortableHaskell/ghcup/bin/` (e.g., `haskell-language-server-9.6.7~2.13.0.0.exe`), NOT in `~/PortableHaskell/ghcup/hls/*/` subdirectories. The subdirectory path does not exist; `du` against it will fail with 'No such file or directory'. Use `du -sh ~/PortableHaskell/ghcup/bin/haskell-language-server*` instead.
- `ghcup list` shows all catalog-known versions (marked `X`), not just locally installed ones. Only versions marked `IS` are actually installed on disk.

## History
- 2026-03-09: Added Portable Haskell path notes; documented that HLS binaries are in ghcup/bin/ not ghcup/hls/*/; noted ghcup list shows catalog versions (X) vs installed (IS); GHC 9.6.7 measured at 3.1 GB (agent@Win-APP)
