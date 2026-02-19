# npm

npm is the default package manager for Node.js.

## Where it stores data

- `~/.npm/_cacache/` — content-addressable package cache
- `~/.npm/_logs/` — debug log files
- `node_modules/` — per-project installed packages (in project root)

## What's safe to delete

- `~/.npm/_cacache/` — package cache, re-downloaded as needed
- `~/.npm/_logs/` — debug logs, not needed for operation
- `node_modules/` in projects you're not actively developing

## What's NOT safe to delete

- `~/.npmrc` — npm configuration file
- `node_modules/` in projects you're currently working on (unless you're about to `npm install`)

## Cleanup commands

```bash
# Clear the npm cache
npm cache clean --force

# Remove debug logs
rm -rf ~/.npm/_logs/

# Verify cache integrity
npm cache verify

# Remove node_modules from a specific project
rm -rf /path/to/project/node_modules
```

## Typical space usage

- `~/.npm/_cacache/`: 500 MB - 5 GB depending on how many packages you install
- `node_modules/`: 100 MB - 1 GB per project (some projects much more)

## Platform notes

- On Windows, the cache lives in `%AppData%/npm-cache/`
- npm cache is shared across all Node versions managed by nvm/fnm

## History

- 2026-02-20: Initial page (seed)
