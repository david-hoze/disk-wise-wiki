# Log Files

System and application logs can accumulate significant disk space over time.

## Where it stores data

- `/var/log/` — system logs (Linux/macOS)
- `~/.local/share/` — some application logs
- `~/Library/Logs/` — macOS application logs
- Application-specific log directories (varies)

## What's safe to delete

- Old rotated logs (`.log.1`, `.log.gz`, etc.)
- Application debug logs you've already reviewed
- Journal logs older than a few weeks

## What's NOT safe to delete

- Current active log files (truncate instead of delete)
- Audit logs if required by policy
- Logs for services you're actively debugging

## Cleanup commands

```bash
# Check log directory size
du -sh /var/log/

# Clear systemd journal logs older than 7 days
sudo journalctl --vacuum-time=7d

# Clear systemd journal logs to max 500MB
sudo journalctl --vacuum-size=500M

# Truncate a specific log file (safer than deleting)
sudo truncate -s 0 /var/log/syslog

# Remove old rotated logs
sudo rm /var/log/*.gz
```

## Typical space usage

- `/var/log/`: 100 MB - 5 GB
- systemd journal: 500 MB - 4 GB (often the largest)
- macOS Console logs: 100 MB - 1 GB

## Platform notes

- On systemd-based Linux, journal is often the biggest space consumer. It has its own retention settings in `/etc/systemd/journald.conf`.
- On macOS, `log show` is the modern way to query logs; files in `/var/log/` are increasingly secondary.

## History

- 2026-02-20: Initial page (seed)
