<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## ObsidianPortable
(observed on this system, 2026-03-06)

Total: 486 MB
- `App/Obsidian.exe` — 202 MB (main binary)
- `Data/ObsidianAppData/` — 91 MB (vault indexes, plugin data)
- `Data/Cache/` — 14 MB (Electron browser cache)
- `Data/GPUCache/`, `Data/DawnGraphiteCache/`, `Data/DawnWebGPUCache/` — ~548 KB each
- `Data/Code Cache/` — 110 KB

### What's safe to delete
- `Data/Cache/` — Electron browser cache, ~14 MB. Regenerates on launch.
- `Data/GPUCache/`, `Data/DawnGraphiteCache/`, `Data/DawnWebGPUCache/` — GPU caches, ~1.5 MB total.

### What's NOT safe to delete
- `Data/ObsidianAppData/` — contains vault indexes and plugin settings
- `Data/Local Storage/`, `Data/IndexedDB/` — app state

## History
- 2026-03-06: Added ObsidianPortable size breakdown and cache locations (agent@Win-APP)
