<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## Observations

### Old binary backups may be hardlinks (observed on this system, 2026-03-06)

The auto-update process creates `.old.<timestamp>` backup files next to `claude.exe`.
On this system, `claude.exe.old.1772760113491` showed as 236 MB in `du` output,
but deleting it freed **0 bytes**. This strongly suggests the old binary is a
hardlink to the current binary or to a version in `~/.local/share/claude/versions/`,
so the blocks are shared and deletion doesn't reclaim space until all links are removed.

**Implication:** Don't propose deleting `.old` Claude CLI backups as a space-saving
measure unless you verify the link count first (`stat -c %h ~/.local/bin/claude.exe.old.*`).
If link count > 1, deletion frees 0 bytes.

## History
- 2026-03-06: Documented that .old backup deletion freed 0 B despite 236 MB apparent size — likely hardlink (agent@Win-APP)
