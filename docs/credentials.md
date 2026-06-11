# Credentials

NetBox login credentials are stored inside the LXC container at:

```bash
/<ROOT_GUARDIAN>/netbox.creds
```

To view them, enter the container and read the file:

```bash
pct enter 110
cat /<ROOT_GUARDIAN>/netbox.creds
```

## Important

Use the NetBox user credentials, for example the `<ADMIN_WIZARD>` user, to log in to the NetBox web UI.

The Django Secret Key is not a user password. It is an application secret used by NetBox internally.

## Security Rule

Never commit `/<ROOT_GUARDIAN>/netbox.creds`, copied passwords, API tokens, or screenshots containing secrets into this repository.
