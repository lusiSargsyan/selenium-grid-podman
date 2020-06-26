# selenium-grid-podman
Run selenium grid hub and nodes in podman containers

## Podman

Podman is an open-source project that is available on most Linux platforms and resides on GitHub. Podman is a daemonless container engine for developing, managing, and running Open Container Initiative (OCI) containers and container images on your Linux System. Podman provides a Docker-compatible command line front end that can simply alias the Docker cli, `alias docker=podman`.

Containers under the control of Podman can either be run by root or by a non-privileged user. Podman manages the entire container ecosystem which includes pods, containers, container images, and container volumes using the libpod library. Podman specializes in all of the commands and functions that help you to maintain and modify OCI container images, such as pulling and tagging. It allows you to create, run, and maintain those containers created from those images in a production environment.

 Podman manages the entire container ecosystem which includes pods, containers, container images, and container volumes using the libpod library.
 
 Source :
 https://podman.io/whatis.html
 
 ## What is a pod
 The Pod concept was introduced by Kubernetes.  Podman pods are similar to the Kubernetes definition. 
 
 https://kubernetes.io/docs/concepts/workloads/pods/pod/
 
A Pod is a group of one or more containers (such as Docker containers), with shared storage/network, and a specification for how to run the containers.
 
 The shared context of a Pod is a set of Linux namespaces, cgroups, and potentially other facets of isolation - the same things that isolate a Docker container. Within a Pod's context, the individual applications may have further sub-isolations applied.

Containers within a Pod share an IP address and port space, and can find each other via localhost. They can also communicate with each other using standard inter-process communications like SystemV semaphores or POSIX shared memory. Containers in different Pods have distinct IP addresses and can not communicate by IPC without special configuration. These containers usually communicate with each other via Pod IP addresses.

## Setup podman
```
sudo yum -y install podman
```

## Amazon Linux 2
The Kubic project provides updated packages for CentOS 7 which can be used unmodified on Amazon Linux 2.
```
sudo curl -L -o /etc/yum.repos.d/devel:kubic:libcontainers:stable.repo https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/CentOS_7/devel:kubic:libcontainers:stable.repo
sudo yum -y install yum-plugin-copr
sudo yum -y copr enable lsm5/container-selinux
sudo yum -y install podman

```
More info
https://podman.io/getting-started/installation

## Setup podman compose

```
pip3 install podman-compose
```
pass --user to install inside regular user home without being root.

Or latest development version from GitHub:
```
pip3 install https://github.com/containers/podman-compose/archive/devel.tar.gz
```
or
```
curl -o /usr/local/bin/podman-compose https://raw.githubusercontent.com/containers/podman-compose/devel/podman_compose.py
chmod +x /usr/local/bin/podman-compose
```




