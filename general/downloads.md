# Downloads Directory

The Downloads folder is one of the most common sources of forgotten large files.

## Where it stores data

- `~/Downloads/` — default browser download location
- `~/Desktop/` — some users save downloads here

## What's safe to delete

- Installer packages (`.dmg`, `.pkg`, `.msi`, `.exe`, `.deb`) after installation
- Archives (`.zip`, `.tar.gz`) already extracted
- ISO files already burned/used
- Old documents you've already moved elsewhere

## What's NOT safe to delete

- Files you downloaded but haven't processed yet
- Installers you might need again (if not easily re-downloaded)

## Cleanup commands

```bash
# Find large files in Downloads
du -sh ~/Downloads/* | sort -rh | head -20

# Find files older than 30 days
find ~/Downloads -type f -mtime +30 -exec ls -lh {} \;

# Find installer files
find ~/Downloads -type f \( -name "*.dmg" -o -name "*.pkg" -o -name "*.msi" -o -name "*.iso" \) -exec ls -lh {} \;
```

## Typical space usage

- 1-20 GB is common
- Power users can accumulate 50+ GB of forgotten downloads

## History

- 2026-02-20: Initial page (seed)
