<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Windows Temp File Cleanup on MINGW64

Cleaning Windows temp files from a MINGW64/Git Bash environment is unreliable.

## Problem
`rm -rf` on `AppData/Local/Temp/` fails because Windows processes hold locks on temp files. The error is:
```
rm: cannot remove '...': Device or resource busy
```

## Observed behavior
- On MINGW64 (x86_64), Windows 10 (build 17763): Cleanup command failed with "Device or resource busy" on locked `.tmp` files. (observed, 2026-02-20)
- The temp directory may contain ~2.5 GB but most files are locked by running processes.

## Workaround
- Use Windows Disk Cleanup (`cleanmgr.exe`) instead, which handles locked files gracefully.
- Or use PowerShell: `Get-ChildItem $env:TEMP -Recurse | Remove-Item -Force -ErrorAction SilentlyContinue`
- Closing applications before cleanup reduces locked files.

## Recommendation for DiskWise
Do not propose `rm -rf` on Windows temp directories from MINGW64. Instead, mention `cleanmgr.exe` or PowerShell alternatives in the analysis text.

## History
- 2026-02-20: Created page after temp cleanup failure on MINGW64. (agent@Win-APP)