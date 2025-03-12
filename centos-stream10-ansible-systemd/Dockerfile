FROM ghcr.io/opinkerfi/ansible-images/centos-stream10-ansible

ARG TARGETARCH
RUN echo "Building for OS: $TARGETARCH"

ARG TARGETOS
RUN echo "Building for OS: $TARGETOS"

ARG TARGETPLATFORM
RUN echo "Building for Platform: $TARGETPLATFORM"

LABEL maintainer="Linux Admins at OK<linux-ops@okhysing.is>"
LABEL org.opencontainers.image.source https://github.com/opinkerfi/ansible-images

ENV container=docker

RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done); \
	rm -f /lib/systemd/system/multi-user.target.wants/*;\
	rm -f /etc/systemd/system/*.wants/*;\
	rm -f /lib/systemd/system/local-fs.target.wants/*; \
	rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
	rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
	rm -f /lib/systemd/system/basic.target.wants/*;\
	rm -f /lib/systemd/system/anaconda.target.wants/*;

VOLUME [ "/sys/fs/cgroup" ]

CMD ["/usr/sbin/init"]
