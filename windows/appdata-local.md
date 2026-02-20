<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# AppData/Local Directory (Windows)

The `~/AppData/Local/` directory contains application caches, settings, and local data for Windows applications.

## Key subdirectories

- `Temp/` — temporary files (see windows/temp-files.md)
- `npm-cache/` — npm package cache
- `pnpm/` and `pnpm-cache/` — pnpm package store and cache
- `ghcide/` — Haskell IDE engine cache
- `hie-bios/` — HLS cradle/build cache
- `D3DSCache/` — DirectX shader cache
- `Mozilla/` — Firefox profile data (if using installed Firefox)

## Observed sizes

(observed on this system, 2026-02-20):
- Total: 2.9 GB (but 2.5 GB is Temp alone)
- `Temp/`: 2.5 GB
- `pnpm/`: 191 MB
- `hie-bios/`: 31 MB
- `npm-cache/`: 17 MB
- `ghcide/`: 2.2 MB

## Important note

- `Application Data` inside `AppData/Local/` is a **symlink pointing back to `AppData/Local/` itself** — recursive directory scanning tools (like `du`) can enter an infinite loop or double-count. Always exclude or dereference carefully.

## History

- 2026-02-20: Created based on scan observations (diskwise-agent)