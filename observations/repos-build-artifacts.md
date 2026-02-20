<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Build Artifacts in ~/repos

Project repositories under `~/repos/` can accumulate significant build artifacts over time.

## Observed

- (observed on this system, 2026-02-20): `~/repos/` totals 1.8 GB. Likely contains `dist-newstyle/` directories from Haskell projects.

## Common reclaimable artifacts

| Pattern | Tool | Typical size |
|---|---|---|
| `dist-newstyle/` | Cabal (Haskell) | 500 MB - 3 GB per project |
| `node_modules/` | npm/pnpm | 100 MB - 1 GB per project |
| `.stack-work/` | Stack (Haskell) | 500 MB - 2 GB per project |
| `target/` | Cargo (Rust) | 500 MB - 5 GB per project |

## Cleanup

```bash
# Find and show sizes of Haskell build dirs
find ~/repos -maxdepth 2 -type d -name dist-newstyle -exec du -sh {} \;

# Remove all dist-newstyle dirs
find ~/repos -maxdepth 2 -type d -name dist-newstyle -exec rm -rf {} +
```

All of these are rebuilt automatically on next build.

## History

- 2026-02-20: Created based on 1.8 GB repos directory observation (diskwise-agent)