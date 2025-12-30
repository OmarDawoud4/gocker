# Goker

A minimal container runtime implementation in Go.
Basically just a wrapper around Linux namespaces and chroot.

## Usage

1. Get a rootfs (alpine is good):
```bash
mkdir rootfs
# download alpine tar and extract to rootfs/
```

2. Build and run:
```bash
go build
sudo ./gocker run /bin/sh
```

## How it works
It uses `CLONE_NEWPID` and `CLONE_NEWUTS` to isolate the process, and `chroot` to isolate the filesystem.
