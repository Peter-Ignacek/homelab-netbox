# Reverse Proxy

This section is reserved for the future reverse proxy setup.

## Planned Setup

- Reverse proxy: Nginx Proxy Manager
- Example public domain: `netbox.ignacek.com`
- Forward target: `https://192.168.1.168:443`
- SSL: Nginx Proxy Manager / Let's Encrypt

## Notes

- Keep the local NetBox endpoint available for troubleshooting.
- If extra authentication is enabled in front of NetBox, remember that API access may also be affected.
- For API automation, either allow `/api/` through the proxy or use a configuration that does not conflict with NetBox token authentication.

## TODO

- Add final Nginx Proxy Manager host settings.
- Add SSL renewal notes.
- Add WebSocket or header notes if needed by the final setup.
