# Docker Images

Docker images are layered filesystem snapshots used to create containers.

## Where it stores data

- `/var/lib/docker/` — Docker root directory (Linux)
- `~/Library/Containers/com.docker.docker/` — Docker Desktop data (macOS)
- `~/.docker/` — Docker client configuration and credentials

## What's safe to delete

- Dangling images (no tag, not used by any container)
- Images for tools/versions you no longer use
- Stopped containers you don't need

## What's NOT safe to delete

- Images actively used by running containers
- Images you need but haven't pushed to a registry yet
- `~/.docker/config.json` — contains registry credentials

## Cleanup commands

```bash
# Show disk usage
docker system df

# Remove dangling images
docker image prune

# Remove all unused images (not just dangling)
docker image prune -a

# Full cleanup: unused images, containers, networks, build cache
docker system prune -a

# Remove specific image
docker rmi image_name:tag

# Remove build cache
docker builder prune
```

## Typical space usage

- Base images: 50-200 MB each (alpine ~5 MB, ubuntu ~70 MB, node ~300 MB)
- Application images: 200 MB - 2 GB each
- Build cache: can grow to 10+ GB on active development machines
- Total: 5-50 GB is common for developers

## Platform notes

- On macOS/Windows, Docker Desktop runs in a VM. Disk reclamation may require restarting Docker Desktop.
- `docker system df` may show misleading reclaimable space on older Docker versions — restart the daemon to refresh.

## History

- 2026-02-20: Initial page (seed)
