FROM registry.fedoraproject.org/fedora:40
LABEL maintainer="Brandon Maier <brandon.maier@gmail.com>"
LABEL description="Container with everything needed to run Buildroot on Fedora"
LABEL url="https://github.com/blmaier/buildroot-docker"

RUN dnf upgrade -y && \
	dnf install -y --setopt=install_weak_deps=False \
		asciidoc \
		bash \
		bc \
		binutils \
		bzip2 \
		ca-certificates \
		cmake \
		cpio \
		cvs \
		diffutils \
		file \
		findutils \
		g++ \
		gcc \
		git \
		git-lfs \
		graphviz \
		gzip \
		make \
		mercurial \
		ncurses-devel \
		patch \
		perl \
		python \
		python3-flake8 \
		python3-magic \
		python3-nose2 \
		python3-pexpect \
		python3-pytest \
		python3-setuptools \
		rsync \
		sed \
		subversion \
		tar \
		unzip \
		w3m \
		wget2 \
		wget2-wget \
		which \
		qemu-system-aarch64-core \
		qemu-system-arm-core \
		qemu-system-x86-core \
		shellcheck \
	&& dnf clean all

RUN useradd -ms /bin/bash br-user && \
	chown -R br-user:br-user /home/br-user

USER br-user
WORKDIR /home/br-user
ENV HOME /home/br-user
