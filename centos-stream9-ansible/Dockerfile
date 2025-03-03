FROM quay.io/centos/centos:stream9

ARG TARGETARCH
RUN echo "Building for OS: $TARGETARCH"

ARG TARGETOS
RUN echo "Building for OS: $TARGETOS"

ARG TARGETPLATFORM
RUN echo "Building for Platform: $TARGETPLATFORM"

LABEL maintainer="Samuel Jon Gunnarsson <samuel.jon.gunnarsson@gmail.com>"

RUN \
    dnf update -y && \
    dnf install -y gcc git openssl-devel python3 python3-libselinux python3-devel sudo systemd systemd-libs systemd-pam nmap-ncat bind-utils && \
    ln -s /usr/bin/python3 /usr/bin/python && \
    dnf clean all && \
    rm -rf /var/cache/dnf/*

ENV SHELL=/bin/bash