# buildroot-docker

Docker image for running Buildroot on a Fedora distro.

## Building

Build using docker-build or podman-build. To build and tag run the following.

> podman build -t docker.io/<username>/buildroot-fedora:40 -t docker.io/<username>/buildroot-fedora:latest .

## Pushing

To push to the Docker registry, run the following.

> podman login -u <username> -p <api-password> docker.io/<username>/buildroot-fedora
> podman push docker.io/<username>/buildroot-fedora:40 docker.io/<username>/buildroot-fedora:latest
