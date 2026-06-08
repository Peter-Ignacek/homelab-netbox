# Maintenance

Basic maintenance commands for the NetBox LXC.

## Enter the Container

Run this on the Proxmox host:

```bash
pct enter 110
```

## Check Services

Run these inside the container:

```bash
systemctl status netbox
systemctl status nginx
systemctl status postgresql
```

## Logs

```bash
journalctl -u netbox -n 100 --no-pager
journalctl -u nginx -n 100 --no-pager
```

## Disk Space

```bash
df -h
```

## Practical Notes

- NetBox depends on PostgreSQL.
- Nginx serves the local HTTPS endpoint.
- If the UI does not load, check `nginx` first, then `netbox`, then disk space.
- If authentication is confusing, check `/root/netbox.creds` inside the container.
