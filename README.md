# nodejs

An [Ansible](https://www.ansible.com) role that installs [Node.js](https://nodejs.org) use the [nodesource](https://github.com/nodesource/distributions) repositories.

<p align="center">
  <img src="https://github.com/dgibbs64/ansible-role-nodejs/assets/4478206/ed4af0e0-f0c2-4329-b667-3d392c62582a">
<br>
</p>
<p align="center">
<a href="https://github.com/dgibbs64/ansible-role-nodejs/actions/workflows/action-molecule.yml"><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/dgibbs64/ansible-role-nodejs/action-molecule.yml?label=molecule&logo=ansible&style=flat-square"></a>
<a href="https://galaxy.ansible.com/dgibbs64/nodejs"><img alt="GitHub tag (latest by date)" src="https://img.shields.io/github/v/tag/dgibbs64/ansible-role-nodejs?color=EE0000&label=release&logo=ansible&style=flat-square"></a>
<a href="https://github.com/dgibbs64/ansible-role-nodejs/blob/main/LICENSE.md"><img src="https://img.shields.io/github/license/gameservermanagers/docker-steamcmd?style=flat-square" alt="MIT License"></a>
</p>

## About

[Node.js](https://nodejs.org) is a free, open-source, cross-platform JavaScript runtime environment that lets developers create servers, web apps, command line tools and scripts. This role installs Node.js using the [nodesource](https://github.com/nodesource/distributions) repositories to install the latest Node.js deb/rpm packages typically allowing for the installation of the newer version of Node.js than is available in the default distro repositories. This role can also remove Node.js and the nodesource repositories.

_Note: this role does not use the nvm method to install Node.JS._

## Requirements

### Supported Distros

- AlmaLinux >= 9
- Amazon Linux 2023
- CentOS >= 9
- Debian >= 11
- Fedora >= 37
- OracleLinux >= 9
- openSUSE Leap >= 15
- Redhat Enterprise Linux >= 9
- Rocky Linux >= 9
- Ubuntu >= 20.04

### Supported Architectures

- x86_64
- aarch64
- armv7l

_Note: if there are any more Debian or RedHat Based distros that are supported please let me know._

## Role Variables

By default this role will setup Node.js LTS version. You can change the version to _current_ or _distro_ by setting the `nodejs_version` variable.

- `lts`: Long Term Support version (default).
- `current`: Latest version.
- `distro`: Version provided by the distribution's package manager.
- `<major>`: A specific Node.js major version, e.g. `20`, `22`, `24`.

The `lts` and `current` values are resolved dynamically at runtime by querying the [nodejs.org release index](https://nodejs.org/download/release/index.json).

```yaml
# nodejs version (lts|current|distro|<major version number>)
nodejs_version: lts
# nodejs state (absent|present)
nodejs_state: present
```

## Dependencies

```yaml
community.general
```

## Example Playbook

```yaml
---
- name: Node.js
  hosts: all
  roles:
    - dgibbs64.nodejs
```

## License

MIT

## Author Information

- [Daniel Gibbs](https://danielgibbs.co.uk)
