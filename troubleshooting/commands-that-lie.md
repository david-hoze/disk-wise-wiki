# Commands That Lie

Some common disk-related commands report misleading information. This page documents known cases.

## `du` vs actual disk usage on macOS APFS

`du -sh` on APFS volumes can report misleading numbers because of clones and snapshots. The space shown may not be reclaimable. Use `diskutil apfs list` to see actual purgeable space.

## `docker system df` after prune

`docker system df` sometimes still shows large reclaimable space immediately after `docker system prune`. This is a display bug in older Docker versions. Restarting the daemon refreshes it.

## `df` vs `du` discrepancy

`df` shows filesystem-level usage (includes deleted-but-open files). `du` shows file-level usage. If `df` shows much more used space than `du` accounts for, look for processes holding deleted files open:

```bash
lsof +L1  # files with link count < 1 (deleted but open)
```

## `npm cache verify` reporting 0 bytes

After `npm cache clean --force`, `npm cache verify` may report the cache has content. This is because verify recreates the cache structure. The actual space is freed.

## History

- 2026-02-20: Initial page (seed)
