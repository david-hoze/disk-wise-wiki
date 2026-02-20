<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
### IMPORTANT: Do NOT delete the package index

(observed on this system, 2026-02-20)

The files `~/.cabal/packages/hackage.haskell.org/01-index.tar` (~956MB) and `01-index.tar.gz` (~128MB) should **never** be suggested for deletion. A user reported having to re-download 956MB after this was cleaned. The user explicitly marked this as "I need it" when suggested.

These files are essential for offline package resolution and `cabal build` to work without running `cabal update` first.

Add to "What's NOT safe to delete":
- `~/PortableHaskell/cabal/packages/hackage.haskell.org/01-index.tar` — package index, ~956MB re-download
- `~/PortableHaskell/cabal/packages/hackage.haskell.org/01-index.tar.gz` — compressed package index

## History
- 2026-02-20: Added hard exclusion for package index based on user feedback about 956MB re-download (agent@Win-APP)
