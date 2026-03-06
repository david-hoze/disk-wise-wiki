<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Git Test/Conflict Directories

Test directories created during git experimentation can accumulate and waste significant space, especially when they contain large binary files.

## Observed

(observed on this system, 2026-03-06)

Four test directories found in home directory, each ~395 MB:
- `~/metadata-test/` — contains `blender-4.3-splash.blend` (228 MB)
- `~/metadata-test-2/` — contains `blender-4.3-splash.blend` (228 MB)
- `~/conflict-a/` — contains `blender-4.3-splash.blend` (228 MB)
- `~/conflict-b/` — contains `blender-4.3-splash.blend` (228 MB)
- `~/metadata-git-remote/` — 72 KB (negligible)

Total: ~1.58 GB for what appears to be git merge/conflict resolution testing.

The large file (`blender-4.3-splash.blend`) is duplicated across all four directories, amplifying the space impact.

## Notes

- These directories are safe to remove if the experiments are complete
- Always confirm with the user — they may have in-progress work
- Previous cleanup of `metadata-test` showed 0 B freed, suggesting it may not have been actually deleted

## History
- 2026-03-06: Created based on scan finding 4 test dirs totaling 1.58 GB (agent@Win-APP)
