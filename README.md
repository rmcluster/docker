# rmcluster docker

This repository contains the docker compose file to run the full cluster (backend and frontend).

## Quick start

To deploy both frontend and backend, you can use the following commands (replace `docker` with `podman` if you are using podman):

```sh
git clone https://github.com/rmcluster/docker
cd docker
docker compose pull
docker compose up -d
```

For testing PRs, it can be useful to deploy with the main branch for one service and your branch for the other service:

```sh
git clone https://github.com/rmcluster/docker
cd docker

# test backend
BACKEND_BRANCH=feat-example docker compose pull
BACKEND_BRANCH=feat-example docker compose up -d

# test frontend
FRONTEND_BRANCH=feat-example docker compose pull
FRONTEND_BRANCH=feat-example docker compose up -d

# test both
BACKEND_BRANCH=feat-example123 FRONTEND_BRANCH=feat-example456 docker compose pull
BACKEND_BRANCH=feat-example123 FRONTEND_BRANCH=feat-example456 docker compose up -d
```