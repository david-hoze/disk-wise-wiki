# MinIO

MinIO is an S3-compatible object storage server.

## Where it stores data

- `~/tools/minio/minio.exe`  the server binary (~108 MB)
- `~/.minio/`  MinIO configuration
- `~/minio/`  default data directory (may be empty if using custom config)

## What's safe to delete

- `~/minio/` data directory if no longer using MinIO for local testing
- `~/.minio/` config if fully uninstalling
- The binary itself if no longer needed

## What's NOT safe to delete

- `~/minio/` if it contains active object storage data you need

## Typical space usage

- Binary: ~108 MB
- Data: varies (can be GBs depending on stored objects)

## History

- 2026-02-20: Initial page (diskwise-agent)