# Kali (Rolling) Ansible Docker Image #

[![CI](https://github.com/threatcode/kali-ansible-docker/workflows/Build/badge.svg?branch=master&event=push)](https://github.com/threatcode/kali-ansible-docker/actions?query=workflow%3ABuild) [![Docker pulls](https://img.shields.io/docker/pulls/threatcode/kali-ansible-docker)](https://hub.docker.com/r/threatcode/kali-ansible-docker/)

Kali Linux (Rolling) Docker container for Ansible playbook and role testing.

## Tags ##

  - `latest`: Latest stable version of Ansible, with Python 3.x.

## How to Build ##

This image is built on Docker Hub automatically any time the upstream OS container is rebuilt, and any time a commit is made or merged to the `master` branch. But if you need to build the image on your own locally, do the following:

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. `cd` into this directory.
  3. Run `docker build --tag threatcode/kali-ansible-docker .`

## How to Use ##

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. Pull this image from Docker Hub: `docker pull threatcode/kali-ansible-docker:latest` (or use the image you built earlier).
  3. Run a container from the image: `docker run --detach --privileged --cgroupns=host --volume=/sys/fs/cgroup:/sys/fs/cgroup:rw threatcode/kali-ansible-docker:latest`.
  4. Use Ansible inside the container:
    a. `docker exec --tty [container_id] env TERM=xterm ansible --version`
    b. `docker exec --tty [container_id] env TERM=xterm ansible-playbook /path/to/ansible/playbook.yml --syntax-check`
