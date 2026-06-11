# Homelab NetBox Lab

Public documentation for my NetBox lab running in a Proxmox homelab.

This repository documents the installation, basic operations, reverse proxy plan, backup approach, and troubleshooting notes for a NetBox instance deployed as an LXC container on Proxmox VE.

## Current Status

- Platform: Proxmox VE 8.4.19
- Container ID: 110
- Hostname / project name: `netboxlab`
- Container type: unprivileged LXC
- OS: Debian 13
- CPU: 2 cores
- RAM: 2048 MiB
- Disk: 4 GB
- Local address: `https://192.168.1.168`
- NetBox version: 4.6.2
- PostgreSQL: 16
- IPv4 Internet: working
- IPv6 Internet: not used

## What This Repo Covers

- NetBox installation through Proxmox VE Helper-Scripts / community-scripts
- Container basics and access commands
- Credentials handling without exposing secrets
- Maintenance commands for NetBox, Nginx, PostgreSQL, logs, and disk usage
- Reverse proxy notes for a future Nginx Proxy Manager setup
- Backup expectations for Proxmox / PBS
- Troubleshooting notes from the first installation

## Repository Layout

```text
.
|-- README.md
|-- CHANGELOG.md
|-- docs
|   |-- backup.md
|   |-- credentials.md
|   |-- install.md
|   |-- maintenance.md
|   |-- reverse-proxy.md
|   `-- troubleshooting.md
`-- .gitignore
```

## Security Notice

Do not commit real passwords, API tokens, private keys, session cookies, `.env` files, or the contents of `/<ROOT_GUARDIAN>/netbox.creds`.

The file `/<ROOT_GUARDIAN>/netbox.creds` exists inside the NetBox LXC and contains sensitive login information. It is referenced in this repository only as an operational note.

## Quick Commands

Check the container from the Proxmox host:

```bash
pct status 110
pct enter 110
```

Inside the container:

```bash
systemctl status netbox
systemctl status nginx
systemctl status postgresql
df -h
```

Read the docs in `docs/` for the full notes.

