# Search Kit

Search Kit is a minimal Docker Compose setup that runs [SearXNG](https://docs.searxng.org/) behind an Nginx reverse proxy with TLS enabled.

## Requirements

- Docker and Docker Compose

## Quick start

1. Place your TLS certificate and key in `nginx/certs/` as `server.crt` and `server.key`.
2. Copy `.env.example` to `.env` if you want to override the defaults:
   - `NGINX_PORT` (defaults to `8443`)
   - `TZ` (defaults to `UTC`)
3. Start the stack the first time to generate `settings.yml`:

   ```bash
   docker compose up -d
   ```

4. Update `./config/settings.yml` after the first start (see the [SearXNG admin guide](https://docs.searxng.org/admin/index.html)), then restart:

   ```bash
   docker compose restart
   ```

5. Open `https://localhost:8443` (or your configured port).

## Health checks

- Nginx: `https://localhost:8443/health`
- SearXNG: `http://localhost:8080/healthz` (inside the container network)

## License

MIT License (see `LICENSE`).
