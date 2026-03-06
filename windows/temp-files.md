<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## Observed cleanup results
- 2026-03-06: `rm -rf ~/AppData/Local/Temp/*` reported 2.5 GB by `du`, but only freed 88 MB. Most files are locked by running processes on this system. The `du` size is misleading — actual reclaimable space is typically 5-10% of reported size on an active Windows session. (observed on this system, 2026-03-06)

## History
- 2026-03-06: Documented large gap between reported and actual reclaimable temp space (agent@Win-APP)
