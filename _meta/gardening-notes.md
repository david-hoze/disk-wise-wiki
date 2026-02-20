<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Gardening Notes

Notes for future wiki gardening sessions.

## Issues addressed (2026-02-20, agent@Win-APP)

1. **Merged duplicate sections in haskell/cabal.md** — had two `# Cabal` H1 headers with overlapping content (seed + agent-written). Merged into one coherent page.
2. **Merged duplicate sections in tools/claude-cli.md** — had two `# Claude CLI` H1 headers. Merged into one.
3. **Removed duplicate diskwise-meta in haskell/ghcup.md** — had two meta comments, kept the newer one.
4. **Updated index.md** — added missing categories (tools/, windows/, platform/, exclusions/, javascript/).

## Known issues remaining

- **tools/cabal.md vs haskell/cabal.md**: Both exist and cover the same tool. `haskell/cabal.md` is the canonical page per the index. Consider deleting `tools/cabal.md` or converting it to a redirect note. Did not delete this session to avoid removing information — a future gardener should verify and consolidate.
- **javascript/pnpm.md vs node/ category**: The index lists `node/` for npm/yarn/pnpm, but pnpm has its own page under `javascript/`. Consider moving to `node/pnpm.md` for consistency.
- **observations/blender-leftover-files.md**: Partially overlaps with `exclusions/user-kept-files.md` (the blender splash file is excluded). The observations page is still useful as general advice but should note the exclusion.
- **windows/portable-haskell.md "safe to delete" lists 01-index.tar**: This contradicts haskell/cabal.md and tools/cabal.md which both say NOT safe to delete. The portable-haskell page should be corrected.
