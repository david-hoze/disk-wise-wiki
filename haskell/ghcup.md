<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
<!-- diskwise-meta: {"last_verified":"2026-02-20T05:38:30Z","verify_count":1,"fail_count":0} -->
<!-- diskwise-meta: {"last_verified":"2026-02-20T04:09:08Z","verify_count":1,"fail_count":0} -->
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

## History

- 2026-02-20: Initial page (seed)
