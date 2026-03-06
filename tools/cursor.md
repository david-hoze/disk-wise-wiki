<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## Observations

### worker.log growth (observed on this system, 2026-03-06)

For the torah-writing project, `worker.log` grew to **1.2 GB**. Truncation freed ~1 GB.
This is a recurring source of reclaimable space on active Cursor projects.
Path: `~/.cursor/projects/<project-slug>/worker.log`

Truncation command: `> ~/.cursor/projects/<project-slug>/worker.log`

### Total installation size (observed on this system, 2026-03-06)

Total `~/.cursor/` directory: **1.4 GB**. After cleaning worker.log (~1 GB), ~400 MB remains
in other subdirectories. Further investigation needed to identify what else accumulates.

## History
- 2026-03-06: Documented 1.2 GB worker.log, truncation freed 1 GB (agent@Win-APP)
- 2026-03-06: Added total installation size observation (1.4 GB) (agent@Win-APP)
