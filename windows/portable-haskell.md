<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
<!-- diskwise-meta: {"last_verified":"2026-02-20T04:07:54Z","verify_count":1,"fail_count":0} -->
# Portable Haskell (Windows)

A self-contained Haskell development environment for Windows, typically bundling GHCup, Cabal, and an MSYS2 environment.

## Where it stores data

- `~/PortableHaskell/ghcup/`  GHCup root (GHC, HLS, binaries)
- `~/PortableHaskell/cabal/`  Cabal root (package store, index)
- `~/PortableHaskell/ghcup/msys64/`  bundled MSYS2 environment

## Key differences from standard layout

- GHCup root is at `~/PortableHaskell/ghcup/` instead of `~/.ghcup/`
- Cabal root is at `~/PortableHaskell/cabal/` instead of `~/.cabal/`
- Paths in wiki pages for GHCup/Cabal/Stack should be adjusted accordingly
- The MSYS2 environment provides the Unix shell and tools

## What's safe to delete

- `~/PortableHaskell/ghcup/cache/`  download cache
- `~/PortableHaskell/cabal/packages/hackage.haskell.org/01-index.tar`  index cache (~1 GB)
- Old GHC versions via `ghcup rm ghc <version>`
- Old HLS versions via `ghcup rm hls <version>`

## Typical space usage

- Total: 5-10 GB is common
- GHC: 1-2 GB per version
- HLS binaries: 300-500 MB
- Cabal package index: ~1 GB (tar + tar.gz)
- MSYS2 base: ~1-2 GB

## History

- 2026-02-20: Initial page based on scan of Windows system (diskwise-agent)