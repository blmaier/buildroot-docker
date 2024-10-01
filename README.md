# buildroot-docker

Docker image for running Buildroot on a Fedora distro.

## Building

Build using docker-compose or podman-compose. To build and tag run the following.

> podman compose build

## Pushing

To push to the Docker registry, run the following.

> podman login -u <username> -p <api-password> docker.io
> podman compose push

## Automated build and push with systemd

Systemd can automatically build and push the Docker images using services. To
setup a user service first install the files under `./services/` to
`~/home/src/.config/systemd/user/` by running the following commands.

```
mkdir -p ~/home/src/.config/systemd/user/
cp ./services/* ~/home/src/.config/systemd/user/
systemctl --user daemon-reload
```

Next you must configure some of the service settings for your setup. Run
`systemctl --user edit buildroot-docker` to open the service override and copy
the below text, replacing the `DOCKER_COMPOSE_FILE` with the path to your local
git repo.

```
[Service]
Environment="DOCKER_COMPOSE_FILE=/home/brandon/work/buildroot-docker/compose.yaml"
```

To kick-off a test build, run the service manually

```
systemctl --user daemon-reload
systemctl --user start buildroot-docker
journalctl --user -xeu buildroot-docker
```
