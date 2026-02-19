# Fast Scanning Techniques

Tips for quickly identifying where disk space is going.

## Start broad, then narrow

```bash
# Level 1: filesystem overview
df -h

# Level 2: top-level directory sizes
du -sh /* 2>/dev/null | sort -rh | head -20

# Level 3: drill into the largest
du -sh /home/*/ 2>/dev/null | sort -rh | head -20
```

## Skip slow directories

Some directories are extremely slow to scan (many small files). Skip them on the first pass:

```bash
# Scan home but skip node_modules and .git
du -sh ~/* --exclude='node_modules' --exclude='.git' 2>/dev/null | sort -rh
```

Note: GNU `du` supports `--exclude`, but macOS `du` does not. On macOS, use `find` with `-not -path` instead.

## Finding the biggest files quickly

```bash
# Top 20 largest files anywhere under home
find ~ -type f -size +100M -exec ls -lh {} \; 2>/dev/null | sort -k5 -rh | head -20
```

## ncdu for interactive exploration

`ncdu` is a curses-based disk usage analyzer. It scans once and lets you browse interactively:

```bash
ncdu ~
```

Available via most package managers (`apt install ncdu`, `brew install ncdu`).

## History

- 2026-02-20: Initial page (seed)
