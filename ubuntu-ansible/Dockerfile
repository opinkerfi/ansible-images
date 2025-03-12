FROM docker.io/ubuntu:latest

ARG TARGETARCH
RUN echo "Building for OS: $TARGETARCH"

ARG TARGETOS
RUN echo "Building for OS: $TARGETOS"

ARG TARGETPLATFORM
RUN echo "Building for Platform: $TARGETPLATFORM"

LABEL maintainer="Linux Admins at OK<linux-ops@okhysing.is>"
LABEL org.opencontainers.image.source https://github.com/opinkerfi/ansible-images

RUN \
    apt update -y && \
    apt install -y apt-utils gcc git python3 python3-dev python3-pip libssl-dev sudo && \
    ln -s /usr/bin/python3 /usr/bin/python && \
    rm -rf /var/lib/apt/lists/*

ENV SHELL=/bin/bash
