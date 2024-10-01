# buildroot-docker

Docker image for running Buildroot on a Fedora distro.

## Building

Build using docker-compose or podman-compose. To build and tag run the following.

> podman compose build

## Pushing

To push to the Docker registry, run the following.

> podman login -u <username> -p <api-password> docker.io
> podman compose push
