<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## Consistently Skipped Items (Updated 2026-02-20)

The following items have been skipped across multiple sessions and should not be proposed unless the user specifically asks:

- **Cabal package index** (`~/PortableHaskell/cabal/packages/hackage.haskell.org/01-index.tar*`): User said "I need it" and had to re-download 956 MB after a previous deletion. Do NOT suggest.
- **Blender splash file** (`~/blender-4.3-splash.blend`, 228 MB): User said "I need it" in one session and "not now" in others. Do NOT suggest.
- **AmSoft tormimam3 backup** (`~/AppData/Roaming/AmSoft/tormimam3_Backup.accde`, 121 MB): User said "Not mine" — this may be managed by another user or process. Do NOT suggest.
- **Haskell build artifacts** (`dist-newstyle` dirs in `~/repos/`): Skipped in all 5+ sessions with "not now". User clearly prefers to keep these. Avoid suggesting unless disk is critically low.

## History
- 2026-02-20: Updated with 6-session skip pattern data; Haskell build artifacts now at 5+ skips (agent@Win-APP)
