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
    - `models` or `schemas` (db: json) (also `converters`) of (json encoder/decoder and DB ORM)
    - `middleware`
    - `handlers` or `controllers`
    - `route`/`router` or `endpoint` or `???`
    - `/config` or `/setting` or `/???` (`CORS`, `NewApp` or `NewServer`, `DB connection`, `Parsing .env`, `DI Container`)
    - `filters` and `paginations`
- where to store? (of clean architecture):
    - `interfaces`???
    - `core`/`domain` or `entities` or `valueobjects` (also `converters`)
    - `business logic` or `services`
    - `repositories` or `aggregates`

## Questions to research

- where to store?:
    - `server.go` or `/server`???
    - `/utils` or `/utility` (I quess in top layer `/pkg`? to re use it or ???)
    - `scrapper`???
    - `app.go` or `main.go` that will build and handle all others (or I can make it in `/cmd/api/main.go` or need to make `/internal/app/main.go` and then give it in `/cmd/api/main.go` like `main() { App.Run() }`)
    - `protobuffers` and grpc files
    - `/migrations`???
    - `/sql` or raw sql queries??? if we have them
    - `/vendor`? and it is nessacary to do???

---

- where/how to implement:
    - DI (Dependency Injection) or it is not nessacary thing?
    - logging, logging levels, how to throw it from bottom to top layers
    - constants and error messages?
    - is needed to make in api layer `ApiResponse` schema? (or there is another wrappers for that `PaginationOut`/`PaginationIn`, `ListPaginatedResponse`, `AuthInSchema`/`AuthOutSchema`/`TokenInSchema`/`TokenOutSchema`, `ProductSchema` that helps to make response more elite, custimizable and etc.)
    - validation, serialization and etc. things

---

VS:

```txt
- http/v1/
    - /handler
        - ???
    - /route
        - ???
```

vs

```txt
- http/v1/
    - /customers
        - handlers.go
        - schemas.go
    - /products
        - handlers.go
        - schemas.go
    - routes.go
```
