# Cargo

Cargo is the Rust package manager and build tool.

## Where it stores data

- `~/.cargo/registry/` — crate source code and index
- `~/.cargo/git/` — git-based dependencies
- `~/.cargo/bin/` — installed binaries
- `target/` — per-project build artifacts (in project root)

## What's safe to delete

- `target/` — per-project build cache, rebuilt on next `cargo build`
- `~/.cargo/registry/cache/` — compressed crate files, re-downloaded as needed
- `~/.cargo/registry/src/` — extracted crate sources, re-extracted from cache

## What's NOT safe to delete

- `~/.cargo/bin/` — installed tools like `cargo-edit`, `ripgrep`, etc.
- `~/.cargo/config.toml` — Cargo configuration

## Cleanup commands

```bash
# Remove project build artifacts
cargo clean

# Remove all target directories recursively (from a workspace root)
find . -name "target" -type d -prune -exec rm -rf {} +

# Install cargo-cache for better cache management
cargo install cargo-cache
cargo cache --autoclean
```

## Typical space usage

- `target/`: 500 MB - 5 GB per project (debug builds are larger)
- `~/.cargo/registry/`: 1-3 GB
- `~/.cargo/git/`: 100 MB - 1 GB

## History

- 2026-02-20: Initial page (seed)
