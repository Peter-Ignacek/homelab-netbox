# Troubleshooting

## Installation Appears Stuck

The installation can stay for a long time on a step similar to:

```text
Configuring NetBox (Patience)
```

This can be normal. If it takes too long, check disk space and service status.

## Basic Checks

Inside the container:

```bash
df -h
systemctl status netbox
systemctl status nginx
journalctl -u netbox -n 100 --no-pager
```

## Missing Password

If the NetBox password is missing, check:

```bash
cat /root/netbox.creds
```

Use the NetBox User / admin credentials for login. The Django Secret Key is not a user password.

## Change the Admin Password

Inside the container:

```bash
cd /opt/netbox/netbox
source /opt/netbox/venv/bin/activate
python3 manage.py changepassword admin
```

## Reverse Proxy Returns 401

If a reverse proxy protection layer is enabled, API requests can be blocked before they reach NetBox.

For automation, check whether `/api/` is allowed through the proxy or whether proxy authentication is interfering with NetBox token authentication.
