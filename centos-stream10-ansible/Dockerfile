FROM quay.io/centos/centos:stream10

# ARG TARGETARCH
# RUN echo "Building for OS: $TARGETARCH"

# ARG TARGETOS
# RUN echo "Building for OS: $TARGETOS"

# ARG TARGETPLATFORM
# RUN echo "Building for Platform: $TARGETPLATFORM"


LABEL maintainer="Linux Admins at OK<linux-ops@okhysing.is>"
LABEL org.opencontainers.image.source https://github.com/opinkerfi/ansible-images
LABEL org.opencontainers.image.description="centos-stream10-ansible for arch: $TARGETARCH os: $TARGETOS platform: $TARGETPLATFORM"

RUN \
    dnf update -y && \
    dnf install -y gcc git openssl-devel python3 python3-libselinux python3-devel sudo systemd systemd-libs systemd-pam nmap-ncat bind-utils && \
    dnf clean all && \
    rm -rf /var/cache/dnf/*

ENV SHELL=/bin/bash