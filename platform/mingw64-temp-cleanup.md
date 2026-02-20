<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
# Windows Temp File Cleanup on MINGW64

Cleaning `~/AppData/Local/Temp/` from a MINGW64 (Git Bash) shell is unreliable.

## Problem
`rm -rf ~/AppData/Local/Temp/*` frequently fails with:
```
rm: cannot remove '...nsuXXXX.tmp': Device or resource busy
```
Windows processes hold locks on temp files, and MINGW64's `rm` cannot skip locked files gracefully — the entire glob operation may report failure even if most files were deleted.

## Workaround
- Do NOT propose `rm -rf ~/AppData/Local/Temp/*` as a cleanup action from MINGW64.
- Instead, suggest using Windows Disk Cleanup (`cleanmgr`) or PowerShell:
  ```powershell
  Get-ChildItem $env:TEMP -Recurse -Force -ErrorAction SilentlyContinue | Remove-Item -Recurse -Force -ErrorAction SilentlyContinue
  ```
- Or mention in analysis text that temp cleanup is best done via Windows tools.

## Observed failure
- On mingw64_nt-10.0-17763 (x86_64): `rm -rf ~/AppData/Local/Temp/*` failed on locked `.tmp` file. (observed on this system, 2026-02-20)

## History
- 2026-02-20: Created based on observed failure in prior session. (agent@Win-APP)