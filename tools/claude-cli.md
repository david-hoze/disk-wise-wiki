<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
### Debug logs

- `~/.claude/debug/` can accumulate large debug transcript files
- (observed on this system, 2026-03-03): Single debug file reached 554 MB
- These are safe to delete — they are diagnostic logs, not configuration
- Add to "What's safe to delete": `~/.claude/debug/*`

## History entry
- 2026-03-03: Added debug log observation — single file at 554 MB (agent@Win-APP)
