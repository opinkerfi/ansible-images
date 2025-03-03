# molecule-docker-images

Dockerfiles used to build a set of images based on currently supported Red Hat and derivative open distros, as well as Ubuntu, ready to be used with Molecule to test Ansible roles.
The images currently available are:

All Dockerfiles are directly derived from those made available by the [Pycontribs](https://github.com/pycontribs) and the
[CentOS-Dockerfiles](https://github.com/CentOS/CentOS-Dockerfiles) projects. 



## Setting up building farm with podman

https://www.youtube.com/watch?v=pK2SWgAaGCg


```shell
# Create a connection from the machine that will initiate the build
podman system connection add x86_remote ssh://user@machine.domain.tld/run/podman/podman.sock # you can info on the socket location from systemctl status podman
# Replace podman build with podman farm build to utilise the farm.
```

# Acknowlegements

This repository is inspired by the work initally done by Nicola Musatti, https://github.com/nmusatti/molecule-docker-images