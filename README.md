# Ansible Role: kops

Ansible role for installing [Kops](https://kops.sigs.k8s.io/).

[![Build Status](https://www.travis-ci.org/PyratLabs/ansible-role-kops.svg?branch=master)](https://www.travis-ci.org/PyratLabs/ansible-role-kops)

## Requirements

This role has been tested on Ansible 2.7.0+ against the following Linux Distributions:

  - Amazon Linux 2
  - CentOS 8
  - CentOS 7
  - Debian 10
  - Fedora 29
  - Fedora 30
  - Fedora 31
  - Ubuntu 18.04 LTS

## Disclaimer

If you have any problems please create a GitHub issue, I maintain this role in
my spare time so I cannot promise a speedy fix delivery.

## Role Variables


| Variable           | Description                                                               | Default Value    |
|--------------------|---------------------------------------------------------------------------|------------------|
| `kops_version`     | Use a specific version of kops, eg. `1.15.0`. Specify `false` for latest. | `false`          |
| `kops_install_dir` | Installation directory for kops.                                          | `$HOME/bin`      |

## Dependencies

No dependencies on other roles.

## Example Playbook

Example playbook for installing to single user:

```yaml
- hosts: workstation
  roles:
     - { role: xanmanning.kops, kops_version: 1.15.0 }
```

Example playbook for installing the latest kops version globally:

```yaml
---
- hosts: workstation
  become: true
  vars:
    kops_install_dir: /opt/kops/bin
  roles:
    - role: xanmanning.kops
```

## License

BSD

## Author Information

[Xan Manning](https://xanmanning.co.uk/)
