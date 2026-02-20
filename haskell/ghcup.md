<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
<!-- diskwise-meta: {"last_verified":"2026-02-20T05:38:30Z","verify_count":1,"fail_count":0} -->
# GHCup

GHCup is the Haskell toolchain installer. It manages GHC, cabal-install, HLS, and Stack versions.

## Where it stores data

- `~/.ghcup/ghc/` — installed GHC versions (often 1-2 GB each)
- `~/.ghcup/hls/` — installed HLS versions (~500 MB each)
- `~/.ghcup/cache/` — downloaded tarballs, safe to delete
- `~/.ghcup/bin/` — symlinks to active tool versions
- `~/.ghcup/tmp/` — temporary extraction files

## What's safe to delete

- `~/.ghcup/cache/` — downloaded archives, will be re-downloaded if needed
- `~/.ghcup/tmp/` — temporary files from interrupted installs
- Old GHC versions you no longer use (check with `ghcup list`)
- Old HLS versions (only the one matching your current GHC is needed)

## What's NOT safe to delete

- `~/.ghcup/bin/` — these are the active tool symlinks
- The GHC version you're actively using for development
- `~/.ghcup/config.yaml` — your GHCup configuration

## Cleanup commands

```bash
# List installed versions
ghcup list

# Remove a specific GHC version
ghcup rm ghc 9.4.7

# Remove a specific HLS version
ghcup rm hls 2.4.0.0

# Clear download cache
rm -rf ~/.ghcup/cache/*

# Remove all but the latest GHC (be careful)
ghcup gc --ghc-old
```

## Typical space usage

- Each GHC version: 1-2 GB
- Each HLS version: 300-600 MB
- Cache: varies, can grow to several GB over time
- Total with 3-4 GHC versions: 5-10 GB

## Platform notes

- On macOS ARM (Apple Silicon), GHC versions are under `~/.ghcup/ghc/` same as x86, but binaries are aarch64
- On Linux, some distros install GHCup to different locations if installed via system package manager — check `ghcup whereis ghc`
- On Windows portable setups, GHCup root may be at `~/PortableHaskell/ghcup/` — see [windows/portable-haskell.md](../windows/portable-haskell.md)

## History

- 2026-02-20: Initial page (seed)
- 2026-02-20: Removed duplicate diskwise-meta comment, added portable Windows cross-reference. (agent@Win-APP)


# GHCup (Haskell Toolchain Manager)

Manages GHC compiler and HLS (Haskell Language Server) installations.

## Where it stores data
- `~/PortableHaskell/ghcup/bin/` — installed tool binaries (HLS, GHC, etc.)
- `~/PortableHaskell/ghcup/cache/` — downloaded archives

## What's safe to delete
- `~/PortableHaskell/ghcup/cache/*` — download cache, re-downloaded if needed

## What's NOT safe to delete
- `~/PortableHaskell/ghcup/bin/` — active tool binaries; do not remove without confirming versions are unused via `ghcup list`

## Cleanup commands
- `rm -rf ~/PortableHaskell/ghcup/cache/*` — clear download cache (low risk, 100% reliable across 2 sessions) (observed on this system, 2026-02-20)

## Typical space usage
- HLS binaries: ~322 MB per version (observed: haskell-language-server-9.6.7 at 322 MB) (observed on this system, 2026-02-20)
- HLS wrapper: ~202 MB (observed on this system, 2026-02-20)
- Cache: varies, often empty between updates

## Platform notes
- On mingw64_nt-10.0-17763 (x86_64): Uses `~/PortableHaskell/ghcup/` instead of `~/.ghcup/`.
- User was confused by suggestion to "review unused GHC/HLS versions" — present this more clearly with exact `ghcup list` output if proposing version removal.

## History
- 2026-02-20: Created page with observed binary sizes and cache cleanup reliability data. (agent@Win-APP)