<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
<!-- diskwise-meta: {"last_verified":"2026-02-20T05:38:22Z","verify_count":1,"fail_count":0} -->
# Portable Applications (Windows)

Portable apps are self-contained applications that run without system-level installation, commonly used on restricted Windows environments.

## Common portable app directories

- `~/FirefoxPortable/` — Firefox browser (~900 MB)
- `~/ObsidianPortable/` — Obsidian note-taking app (~450 MB)
- `~/PortableHaskell/` — Haskell development toolchain (5-10 GB). See [windows/portable-haskell.md](../windows/portable-haskell.md).

## What's safe to delete

- Browser caches inside `~/FirefoxPortable/Data/profile/cache2/`
- Obsidian plugin caches
- The entire app directory if the tool is no longer needed (portable apps have no external dependencies to clean up)

## What's NOT safe to delete

- `~/FirefoxPortable/Data/profile/` — contains bookmarks, saved passwords, browsing history
- `~/ObsidianPortable/` vaults and configuration if you have notes stored there

## Notes

- Portable apps can accumulate caches and update artifacts that aren't cleaned automatically
- Because they're self-contained, removing the entire directory is a clean uninstall
- On space-constrained systems, these apps can consume significant disk relative to installed equivalents due to bundled runtimes

## History

- 2026-02-20: Initial page (diskwise-agent)
- 2026-02-20: Removed duplicate diskwise-meta comment, added cross-reference to portable-haskell page. (agent@Win-APP)
