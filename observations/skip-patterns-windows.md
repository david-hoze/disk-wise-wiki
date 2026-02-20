<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## Updated observations (2026-02-20, 6 sessions)

### Haskell build artifacts — persistent "not now" pattern
The user has skipped dist-newstyle cleanup 4 times with "not now". This is ambiguous — they may want per-project cleanup with size visibility rather than bulk deletion. Future suggestions should:
1. List each project's dist-newstyle size individually
2. Propose individual `rm -rf ~/repos/<project>/dist-newstyle` commands
3. Not use bulk `find -exec` patterns

### Confirmed permanent exclusions
- Cabal package index: user said "I need it" and reported 956MB re-download cost
- Blender splash file: user said "I need it"
- AmSoft backup: user said "Not mine" (externally managed)

### Command reliability (6 sessions)
- `rm -rf ~/FirefoxPortable/Data/profile/cache2/*`: 100% (3/3)
- `rm -rf ~/PortableHaskell/ghcup/cache/*`: 100% (3/3)
- `rm -rf ~/PortableHaskell/cabal/logs/*`: 100% (2/2)
- `rm -rf ~/AppData/Local/Temp/*`: failed once (device busy) — expected on Windows

### Average space freed: ~129 MB/session

## History
- 2026-02-20: Updated with 6-session analysis of skip patterns and command reliability (agent@Win-APP)
