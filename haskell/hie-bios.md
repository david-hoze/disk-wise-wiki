<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# hie-bios (HLS cradle cache)

hie-bios caches Haskell Language Server project cradle information.

## Where it stores data
- `~/.hie-bios/` — cradle cache files

## What's safe to delete
- Entire `~/.hie-bios/` directory. Rebuilds automatically when HLS next loads a project. Low risk.

## Cleanup commands
```bash
rm -rf ~/.hie-bios/
```

## Typical space usage
- ~29-31 MB (observed on this system, 2026-02-20)

## History
- 2026-02-20: Created page. Confirmed ~29 MB freed matches estimate of ~31 MB. (agent@Win-APP)