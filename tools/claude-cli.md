<!-- diskwise-meta: {"last_verified":null,"verify_count":0,"fail_count":0} -->
## Old version accumulation
Claude CLI keeps old versions in `~/.local/share/claude/versions/`. Each version is ~236 MB. Only the version matching `~/.local/bin/claude.exe` is needed.

- 2026-03-06: Found versions 2.1.69 and 2.1.70 both present (472 MB total, ~236 MB reclaimable). (observed on this system, 2026-03-06)

### Cleanup
```bash
# List versions and remove old ones (keep the latest)
ls -la ~/.local/share/claude/versions/
# Remove specific old version:
rm -rf ~/.local/share/claude/versions/2.1.69
```

## History
- 2026-03-06: Documented old version accumulation pattern (agent@Win-APP)
