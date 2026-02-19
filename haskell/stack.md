# Stack

Stack is an alternative Haskell build tool that manages its own GHC installations and package snapshots.

## Where it stores data

- `~/.stack/` — global Stack root
- `~/.stack/programs/` — GHC installations managed by Stack
- `~/.stack/snapshots/` — compiled snapshot packages
- `~/.stack/pantry/` — package index and downloaded sources
- `.stack-work/` — per-project build artifacts (in project root)

## What's safe to delete

- `.stack-work/` — per-project build cache, rebuilt on next `stack build`
- `~/.stack/pantry/` — re-downloaded on next build
- Old snapshot directories for resolvers you no longer use

## What's NOT safe to delete

- `~/.stack/programs/` GHC versions you actively use
- `~/.stack/config.yaml` — global Stack configuration

## Cleanup commands

```bash
# Remove project build artifacts
rm -rf .stack-work/

# Clean Stack's download cache
stack purge

# Remove old snapshots (manual)
ls ~/.stack/snapshots/
# Then rm -rf specific old ones
```

## Typical space usage

- `~/.stack/programs/`: 1-2 GB per GHC version
- `~/.stack/snapshots/`: 1-5 GB per resolver
- `.stack-work/`: 500 MB - 2 GB per project
- Total: can easily reach 10-20 GB

## History

- 2026-02-20: Initial page (seed)
