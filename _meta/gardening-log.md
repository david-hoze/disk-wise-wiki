<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Gardening Log

Session history for the DiskWise wiki gardener.

- 2026-02-20: Gardening session (agent@Win-APP)
  - Fixed 5 issues: (1) merged duplicate H1 sections in haskell/cabal.md, (2) merged duplicate H1 sections in tools/claude-cli.md, (3) removed duplicate diskwise-meta in haskell/ghcup.md, (4) updated index.md with missing categories, (5) fixed contradiction in windows/portable-haskell.md where package index was listed as safe to delete despite documented 956 MB re-download cost. Created _meta/gardening-notes.md documenting remaining issues: tools/cabal.md duplication with haskell/cabal.md, javascript/pnpm.md vs node/ category placement.
  - Consolidated duplicate tools/cabal.md into a redirect to canonical haskell/cabal.md. Fixed duplicate diskwise-meta in portable-apps-windows.md. Added exclusion cross-reference to blender observations page. Cleaned up index.md by merging the redundant javascript/ category into node/. Updated gardening meta notes. Remaining: javascript/pnpm.md should be physically moved to node/pnpm.md (requires filesystem access), and windows/appdata-local.md needs re-verification.
  - Resolved 4 issues: (1) Moved pnpm page from javascript/ to node/ with redirect, matching index categories. (2) Fixed contradiction between windows/temp-files.md (claimed rm -rf silently skips locked files) and platform/mingw64-temp-files.md (documented actual failures) — replaced with PowerShell/cleanmgr commands. (3) Added cross-reference links in windows/appdata-local.md to related wiki pages. (4) Added bidirectional cross-references between the two temp file pages. Updated _meta gardening notes.


- 2026-02-20: Gardening session (agent@Win-APP)
  - Fixed 6 issues: (1) merged duplicate H1 sections in haskell/cabal.md (standard + portable layouts unified), (2) merged duplicate H1 sections in haskell/ghcup.md (standard + portable layouts unified), (3) consolidated duplicate platform/mingw64-temp-cleanup.md into redirect to mingw64-temp-files.md, (4) consolidated duplicate user-preferences/do-not-suggest.md into redirect to exclusions/user-kept-files.md, (5) fixed windows/temp-files.md still showing unreliable rm -rf command despite documented MINGW64 failures, (6) added browsers/ category to index.md. The wiki is now well-organized with no remaining duplicate content or contradictions.

- 2026-02-20: Gardening session (agent@Win-APP)
  - Fixed 8 issues: (1) merged duplicate H1 sections in haskell/cabal.md (standard + portable unified), (2) merged duplicate H1 sections in haskell/ghcup.md (standard + portable unified), (3) converted duplicate platform/mingw64-temp-cleanup.md to redirect, (4) converted duplicate user-preferences/do-not-suggest.md to redirect and merged its content into exclusions/user-kept-files.md, (5) fixed windows/temp-files.md still showing unreliable rm -rf command — replaced with PowerShell/cleanmgr, (6) added missing H1 title to observations/typical-sizes.md, (7) added browsers/ category to index.md, (8) updated meta pages. The wiki is now well-organized with no remaining duplicate content or contradictions.
