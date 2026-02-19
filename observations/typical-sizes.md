# Typical Sizes

Observations about how much space common tools and directories typically consume on real systems.

## Development tools

| Tool/Directory | Typical Range | Notes |
|---|---|---|
| `~/.ghcup/` | 5-15 GB | Grows with each GHC version |
| `~/.cabal/store/` | 2-10 GB per GHC version | |
| `dist-newstyle/` | 500 MB - 3 GB per project | |
| `.stack-work/` | 500 MB - 2 GB per project | |
| `~/.npm/` | 500 MB - 5 GB | |
| `node_modules/` | 100 MB - 1 GB per project | Some projects much more |
| `~/.cargo/` | 1-5 GB | |
| `~/.rustup/` | 1-3 GB | Per toolchain |
| Docker images | 5-50 GB total | Varies wildly |

## System directories

| Directory | Typical Range | Notes |
|---|---|---|
| `/var/log/` | 100 MB - 5 GB | Journal often the largest part |
| `~/Downloads/` | 1-20 GB | Frequently forgotten |
| `~/.cache/` | 1-10 GB | Aggregates many app caches |
| `/tmp/` | 100 MB - 2 GB | Usually cleared on reboot |

## Things that grow surprisingly fast

- Docker build cache: can exceed 20 GB in a week of active development
- Xcode derived data: 10+ GB per major Xcode version
- JetBrains IDE caches: 2-5 GB per IDE
- Homebrew cache: 2-10 GB if not cleaned periodically

## History

- 2026-02-20: Initial page (seed)
