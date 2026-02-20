<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Windows Temp Files (AppData/Local/Temp)

Windows and applications store temporary files in `~/AppData/Local/Temp/`.

## Where it stores data

- `~/AppData/Local/Temp/` — the primary user temp directory

## What's safe to delete

- Everything in this directory is intended to be temporary
- Files locked by running processes will fail to delete (harmless)
- Old files (more than a few days) are almost always safe

## What's NOT safe to delete

- Files actively in use by running applications (the OS will prevent deletion anyway)

## Cleanup commands

```bash
# Delete all temp files (locked files will be skipped)
rm -rf ~/AppData/Local/Temp/*
```

## Typical space usage

- (observed on this system, 2026-02-20): 2.5 GB accumulated
- Can grow unbounded if never cleaned; 1-5 GB is common on long-running Windows systems

## Platform notes

- On MINGW/Git Bash, the path is `/c/Users/<user>/AppData/Local/Temp/`
- `rm -rf` will silently skip locked files; this is safe to run while applications are open
- The `Application Data` symlink in `AppData/Local/` points back to itself — avoid following it with recursive tools to prevent infinite loops

## History

- 2026-02-20: Created based on finding 2.5 GB of temp files (diskwise-agent)