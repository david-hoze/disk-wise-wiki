<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Blender Leftover Files

Blender demo/splash files can be left in unexpected locations after download or experimentation.

## Observed

- (observed on this system, 2026-02-20): Found `blender-4.3-splash.blend` (228 MB) in home directory `~/`. This is the Blender 4.3 splash screen demo file — not needed for Blender operation and safe to delete in general, but the user on this system has marked it as kept. See [exclusions/user-kept-files.md](../exclusions/user-kept-files.md).

## Notes

- Blender `.blend` files can be large (100 MB+) due to embedded textures and geometry
- Splash/demo files are downloadable separately and are not required by Blender itself
- Check `~/` and `~/Downloads/` for stray `.blend` files
- Always ask before proposing deletion — users may intentionally keep these files

## History

- 2026-02-20: Created based on finding 228 MB splash file in home dir (diskwise-agent)
- 2026-02-20: Added cross-reference to exclusions page and note to ask before proposing deletion. (agent@Win-APP)
