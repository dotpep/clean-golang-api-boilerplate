# `/internal`

Layer that cannot be imported outside of project, like `/pkg`, `/internal` is only internal thing of project.

## Layers

- `/api`
- `/config`

Clean Architecure layers/pwds:

- `/services`
- `/repositories`

API layers (`/api/`):

- `/http/v1` (is REST API)
- `/grpc`

---

Questions:

- where to store? (api):
    - `models` or `schemas` (db: json) (also `converters`)
    - `middleware`
    - `handlers` or `controllers`
    - `route` or `endpoint` or `???`
- where to store? (of clean architecture):
    - `interfaces`
    - `core` or `entities` or `valueobjects` (also `converters`)
    - `business logic` or `services`
    - `repositories` or `aggregates`

## Questions to research

- where to store?:
    - `server.go`
    - `/utils` or `/utility` (I quess in top layer `/pkg`? to re use it or ???)
    - `scrapper`???
