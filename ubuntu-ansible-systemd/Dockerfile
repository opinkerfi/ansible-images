FROM ghcr.io/opinkerfi/ansible-images/ubuntu-ansible

LABEL maintainer="Linux Admins at OK<linux-ops@okhysing.is>"
LABEL org.opencontainers.image.source https://github.com/opinkerfi/ansible-images

ARG TARGETARCH
RUN echo "Building for OS: $TARGETARCH"

ARG TARGETOS
RUN echo "Building for OS: $TARGETOS"

ARG TARGETPLATFORM
RUN echo "Building for Platform: $TARGETPLATFORM"

ENV container=docker

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update ; \
    apt-get install -y systemd systemd-sysv ; \
    apt-get clean ; \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* ; \
    cd /lib/systemd/system/sysinit.target.wants/ ; \
    ls | grep -v systemd-tmpfiles-setup | xargs rm -f $1 ; \
    rm -f /lib/systemd/system/multi-user.target.wants/* ; \
    rm -f /etc/systemd/system/*.wants/* ; \
    rm -f /lib/systemd/system/local-fs.target.wants/* ; \
    rm -f /lib/systemd/system/sockets.target.wants/*udev* ; \
    rm -f /lib/systemd/system/sockets.target.wants/*initctl* ; \
    rm -f /lib/systemd/system/basic.target.wants/* ; \
    rm -f /lib/systemd/system/anaconda.target.wants/* ; \
    rm -f /lib/systemd/system/plymouth* ; \
    rm -f /lib/systemd/system/systemd-update-utmp*

VOLUME [ "/sys/fs/cgroup" ]

CMD ["/usr/sbin/init"]
