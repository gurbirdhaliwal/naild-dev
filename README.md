# Naild Dev Workspace

Single entry point to run all services (frontend, python backend, Spring Boot).

## Recommended folder layout

Clone the three repos as siblings under the same parent directory:

- naild-dev (this repo)
- Naild-WebApp
- security

If your repos are elsewhere, set paths in a local `.env` (not committed).

## Quick start

1. From this repo:

```bash
docker compose up --build
```

2. Services:

- Frontend: http://localhost:3000
- Python backend: http://localhost:8081
- Spring Boot: http://localhost:8080

## Local overrides

Create a `.env` file in this repo to override paths or ports. Example:

```bash
NAILD_WEBAPP_PATH=../Naild-WebApp/naild-website
SPRINGBOOT_PATH=../security
```

If your Spring repo is in `~/Downloads/security` (current local layout):

```bash
SPRINGBOOT_PATH=../Downloads/security
```

## Notes

- Frontend uses `localhost:8080` so the browser can reach Spring Boot.
- Python backend uses `springboot:8080` for container-to-container calls.
- Spring Boot changes require rebuilds unless you run it outside Docker.
