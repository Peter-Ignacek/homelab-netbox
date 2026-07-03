# Installation

NetBox was installed on Proxmox VE using Proxmox VE Helper-Scripts / community-scripts.

The helper script creates an LXC container and installs NetBox automatically. This repo documents the resulting lab setup and the operational commands used after installation.

## Environment

- Proxmox VE: 8.4.19
- Container ID: 110
- Hostname / project name: `netboxlab`
- Container type: unprivileged LXC
- System: Debian 13
- CPU: 2 cores
- RAM: 2048 MiB
- Disk: 4 GB
- Local address: `https://<PRIVATE_IP>`
- NetBox version: 4.6.2
- PostgreSQL: 16
- IPv4 Internet: working
- IPv6 Internet: not used

## Container Status

Run these commands on the Proxmox host:

```bash
pct status 110
pct enter 110
```

`pct status 110` shows whether the container is running.

`pct enter 110` opens a shell inside the NetBox container.

## Notes

During installation, the helper script may spend a long time on a step similar to:

```text
Configuring NetBox (Patience)
```

This can be normal. If it takes too long, check disk space and service status from another shell.
