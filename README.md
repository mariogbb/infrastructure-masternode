# infrastructure-masternode
Infrastructure services for my main homelab node

The root `compose.yml` deploys the managed services through Dokploy as one
project, excluding Dokploy itself and Convoy.
See [MIGRATION.md](MIGRATION.md) before replacing an existing deployment.

## Services

- `authentik`: Copy `authentik/.env.example` to `authentik/.env`, set its secrets, then run `docker compose --env-file authentik/.env -f authentik/compose.yml up -d` (web UI: `https://<host>:9443`)
- `convoy`: Copy `convoy/.env.example` to `convoy/.env`, set its secrets and public URL, then run `docker compose --env-file convoy/.env -f convoy/compose.yml up -d` (web UI: `http://<host>:5005`)
- `dockploy`: `docker compose -f dockploy/compose.yml up -d` (web UI: `http://<host>:3000`)
- `glances`: `docker compose -f glances/compose.yml up -d` (web UI: `http://<host>:61208`)
- `hermes`: `docker compose -f hermes/compose.yml up -d`
- `n8n`: `docker compose -f n8n/compose.yml up -d`
- `plex`: Create `plex/media`, optionally set `PLEX_CLAIM`, then run `docker compose -f plex/compose.yml up -d` (web UI: `http://<host>:32400/web`)
- `portainer`: `docker compose -f portainer/compose.yml up -d`
- `silverbullet`: `docker compose -f silverbullet/compose.yml up -d`
- `snapotter`: Copy `snapotter/.env.example` to `snapotter/.env`, set `POSTGRES_PASSWORD`, then run `docker compose --env-file snapotter/.env -f snapotter/compose.yml up -d` (web UI: `http://<host>:1349`; default login: `admin` / `admin`)
- `syncthing`: Create `syncthing/data`, then run `docker compose -f syncthing/compose.yml up -d` (web UI: `http://<host>:8384`)
- `termix`: `docker compose -f termix/compose.yml up -d` (web UI: `http://<host>:8080`)
