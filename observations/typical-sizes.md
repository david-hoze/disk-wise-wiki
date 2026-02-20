<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## Observed sizes on Windows portable environment (2026-02-20)

| Directory | Size | Notes |
|-----------|------|-------|
| `~/PortableHaskell/` | 7.7 GB | GHCup + Cabal + GHC toolchain |
| `~/repos/` | 1.8 GB | Projects, may include dist-newstyle |
| `~/tools/` | 1.1 GB | Portable tools (PortableGit, MinIO, etc.) |
| `~/AppData/` | 852 MB | Application data |
| `~/FirefoxPortable/` | 511 MB | Browser + cache |
| `~/ObsidianPortable/` | 452 MB | Note-taking app |
| `~/.local/` | 447 MB | Claude CLI (~224MB binary + versions) |
| `~/.claude/` | 245 MB | Claude CLI config/data |
| Disk total | 127 GB, 93% used (9.8 GB free) | |

Largest single files:
- `01-index.tar`: 956 MB (Cabal package index — DO NOT DELETE)
- `haskell-language-server-9.6.7`: 322 MB
- `haskell-language-server-wrapper`: 202 MB
- `blender-4.3-splash.blend`: 228 MB (user-kept)
- `claude.exe`: 224 MB

## History
- 2026-02-20: Added comprehensive size snapshot from scan (agent@Win-APP)
