# Search Kit

Search Kit is a minimal Docker Compose setup that runs [SearXNG](https://docs.searxng.org/) behind an Nginx reverse proxy with TLS enabled.

## Requirements

- Docker and Docker Compose

## Quick start

1. Place your TLS certificate and key in `nginx/certs/` as `server.crt` and `server.key`.
2. Add your SearXNG configuration in `./config/` (mounted at `/etc/searxng/`).
3. (Optional) Create a `.env` file to set:
   - `TZ` (defaults to `UTC`)
   - `NGINX_PORT` (defaults to `8443`)
4. Start the stack:

   ```bash
   docker compose up -d
   ```

5. Open `https://localhost:8443` (or your configured port).

## Health checks

- Nginx: `https://localhost:8443/health`
- SearXNG: `http://localhost:8080/healthz` (inside the container network)

## Suggested license

MIT License (see `LICENSE`). If you prefer a different license, replace the file accordingly.
