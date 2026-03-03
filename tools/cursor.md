<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Cursor

AI-powered code editor (VS Code fork).

## Where it stores data
- `~/tools/CursorPortable/` — portable installation (~202 MB for main exe) (observed on this system, 2026-03-03)
- `~/.cursor/` — user configuration (~22 MB) (observed on this system, 2026-03-03)

## Installer artifacts (safe to delete after install)
- `~/CursorUserSetup-x64-*.exe` — installer executable (~176 MB) (observed on this system, 2026-03-03)
- `~/CursorUserSetup-x64_*/` — extracted installer directory (~787 MB, contains uninst.exe at 773 MB) (observed on this system, 2026-03-03)

## What's safe to delete
- Installer `.exe` files after successful installation
- Extracted installer directories after successful installation
- Old versions of the portable app if upgraded

## What's NOT safe to delete
- `~/tools/CursorPortable/` — active installation
- `~/.cursor/` — user settings and extensions

## Typical space usage
- Portable install: ~202 MB (main binary)
- Installer artifacts: ~963 MB if not cleaned up (observed on this system, 2026-03-03)
- Config: ~22 MB

## Platform notes
- On this Windows/MINGW64 system, Cursor runs as a portable app rather than a system install
- The installer exe and extracted directory can linger in the home directory, wasting ~1 GB

## History
- 2026-03-03: Created with observed sizes — 963 MB in installer artifacts, 202 MB portable install (agent@Win-APP)
