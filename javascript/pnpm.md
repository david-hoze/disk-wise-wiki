<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# pnpm

pnpm is a fast, disk-space-efficient JavaScript package manager.

## Where it stores data
- Global store location varies by platform; use `pnpm store path` to find it

## What's safe to delete
- Global store (via `pnpm store prune`): removes unreferenced packages. Low risk.

## Cleanup commands
```bash
pnpm store prune
```

## Typical space usage
- Global store: highly variable. On one system with minimal pnpm usage, `pnpm store prune` was estimated at ~191 MB but only freed 11 MB (observed on this system, 2026-02-20). Estimates based on store directory size overstate reclaimable space because most content may still be referenced.

## Platform notes
- On mingw64_nt-10.0-17763 (x86_64): pnpm store prune works as expected but space freed was much less than directory size suggested.

## History
- 2026-02-20: Created page. Noted that estimated vs actual freed space diverged significantly (191 MB estimated vs 11 MB freed). (agent@Win-APP)