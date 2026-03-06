<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## Worker logs

- `~/.cursor/projects/*/worker.log` — per-project worker logs that can grow very large
- (observed on this system, 2026-03-06): Single worker.log reached 1.2 GB for one project
- Safe to truncate (`truncate -s 0`) or delete — these are runtime diagnostic logs
- Cursor recreates the file as needed

### History entry
- 2026-03-06: Added worker.log observation — 1.2 GB single file (agent@Win-APP)
