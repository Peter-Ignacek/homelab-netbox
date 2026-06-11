# Backup

The NetBox LXC should be covered by regular Proxmox / Proxmox Backup Server backups.

NetBox uses PostgreSQL, so a reliable backup strategy matters. A full CT backup is a good baseline for a lab setup.

## Recommended Baseline

- Include CT `110` in the Proxmox / PBS backup schedule.
- Keep regular backups before NetBox upgrades.
- Test restore procedures before relying on the instance for critical inventory.

## Security Notes

- Do not store backup archives in this repository.
- Do not commit exported backups containing passwords, API tokens, or private infrastructure data.
- Do not commit `/<ROOT_GUARDIAN>/netbox.creds`.

## Future Improvements

- Add a PostgreSQL dump procedure.
- Add a restore checklist.
- Add pre-upgrade snapshot notes.
