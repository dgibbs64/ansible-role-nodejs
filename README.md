# nodejs

An [Ansible](https://www.ansible.com) role that installs [Node.js](https://nodejs.org).

## About

[Node.js](https://nodejs.org) is a free, open-source, cross-platform JavaScript runtime environment that lets developers create servers, web apps, command line tools and scripts.

## Requirements

None.

## Role Variables

By default this role will setup Node.js LTS version. You can change the version to _current_ or _distro_ by setting the `nodejs_version` variable.

- LTS: Long Term Suport version
- Current: Latest version
- Distro: Version provided by the distribution

```yaml
# nodejs version (lts|current|distro)
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
