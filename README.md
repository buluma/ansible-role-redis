# Ansible role [redis](https://galaxy.ansible.com/ui/standalone/roles/buluma/redis/documentation)

Install and configure redis on your system.

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-redis/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-redis/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-redis.svg)](https://github.com/buluma/ansible-role-redis/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-redis.svg)](https://github.com/buluma/ansible-role-redis/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-redis.svg)](https://github.com/buluma/ansible-role-redis/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/redis)](https://galaxy.ansible.com/ui/standalone/roles/buluma/redis/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-redis/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.redis
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-redis/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  gather_facts: no
  become: yes

  roles:
    - role: buluma.bootstrap
    - role: buluma.epel
    - role: buluma.apt_autostart
    - role: buluma.sysctl
      sysctl_items:
        - name: vm.overcommit_memory
          value: 1
    - role: robertdebock.grub
      # TODO: build grub
      grub_options:
        - option: transparent_hugepage
          value: never
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.


## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-redis/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.apt_autostart](https://galaxy.ansible.com/buluma/apt_autostart)|[![Ansible Molecule](https://github.com/buluma/ansible-role-apt_autostart/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-apt_autostart/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-apt_autostart.svg)](https://github.com/shadowwalker/ansible-role-apt_autostart)|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.epel](https://galaxy.ansible.com/buluma/epel)|[![Ansible Molecule](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-epel.svg)](https://github.com/shadowwalker/ansible-role-epel)|
|[buluma.sysctl](https://galaxy.ansible.com/buluma/sysctl)|[![Ansible Molecule](https://github.com/buluma/ansible-role-sysctl/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-sysctl/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-sysctl.svg)](https://github.com/shadowwalker/ansible-role-sysctl)|
|[robertdebock.grub](https://galaxy.ansible.com/buluma/robertdebock.grub)|[![Ansible Molecule](https://github.com/buluma/robertdebock.grub/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/robertdebock.grub/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/robertdebock.grub.svg)](https://github.com/shadowwalker/robertdebock.grub)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-redis/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Alpine](https://hub.docker.com/repository/docker/buluma/alpine/general)|all|
|[EL](https://hub.docker.com/repository/docker/buluma/enterpriselinux/general)|8|
|[Debian](https://hub.docker.com/repository/docker/buluma/debian/general)|all|
|[Fedora](https://hub.docker.com/repository/docker/buluma/fedora/general)|all|
|[opensuse](https://hub.docker.com/repository/docker/buluma/opensuse/general)|all|
|[Ubuntu](https://hub.docker.com/repository/docker/buluma/ubuntu/general)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-redis/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-redis/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-redis/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)


Template inspired by [Robert de Bock](https://github.com/robertdebock)
