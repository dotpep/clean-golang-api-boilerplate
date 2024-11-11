# Golang Clean Codebase/Dirs structure for web/api (boilerblate, template and example)

[Standard Go Project Layout](https://github.com/golang-standards/project-layout)

## Notes

- `/cmd` is main entrypoint for compiling executable files of Golang projects

Technologies:

- `Makefile` - aliases for cli/cmd commands
- `.env` - secrets (environment variable)
- `/configs/main.yml` - cfg constants/variables of our project
- `/docs/swagger` or just `/docs` can store swagger/openapi generated documentation and other things like ER-D of projects

Top layers:

- `/src`
    - will hold static files of GitHub repository
    - or we can store it in `/docs/src/`???
    - also if our project repo is for fullstack we can store statics of frontend in `/src` or `/internal/statics/`???

Sub layers:

### Docker, K8s and Dev/Prod staging Containers/Docker Composes

`docker-compose.yml` is for development stage
`/deployments/docker-compose.yml` or other or etc. things like for K8s for depleyments

Also we can divide our Dev stage docker-compose into: `/docker_compose/app.yml` and `/docker_compose/storages.yml`

- furthermore for better/comfort run our docker-composes or anything else we can use `Makefile` in Top layer

### About Tests, Unit Test, Integrate tests

we can store all tests in Top level layer: `/tests` or `/test`,
and also we can store tests in `/internal` like specific for Unit Tests and then Integrate tests will be in Top layer `/tests` and Unit tests in `/internal/tests/some_unit_tests.go`

###
