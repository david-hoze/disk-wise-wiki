<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Skip Pattern Observations — Windows Portable Environment

Notes on actions that users frequently skip or reject, to calibrate future recommendations.

## Files users consider essential despite appearing removable

- **Blender splash .blend files in home directory** — User stated "I need it". Do not propose removing `.blend` files without asking first. (observed 2026-02-20)
- **AmSoft .accde backup files** — User stated "Not mine" (shared machine or managed by someone else). Do not propose removing application data in `AppData/Roaming/` belonging to shared or managed applications without confirming ownership. (observed 2026-02-20)

## Actions that caused problems

- **Cabal package index deletion** — Proposed as low-risk cache cleanup. User had to re-download 956MB. Should be medium-to-high risk for active Haskell users. See [cabal.md](../haskell/cabal.md). (observed 2026-02-20)

## Lessons for portable/shared environments

- On portable Windows setups, files in the home directory may be intentionally placed there (not just clutter).
- `AppData/Roaming/` may contain data managed by other users or IT — confirm ownership before proposing deletion.
- Package manager caches that are "just a re-download" can be very large (nearly 1GB) and painful on constrained connections.

## History

- 2026-02-20: Created page from session review. Documented 3 skip patterns and 1 user-reported problem. (agent@Win-APP)