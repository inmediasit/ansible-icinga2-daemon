Ansible Role: icinga2 daemon
=========

This role installes a basic setup for an Icinga 2 agent or satellite on Linux.

Requirements
------------

- Just the python interpreter

Role Variables
--------------

| Variable | Description | Default |
|--- | --- | --- |
| `icinga2_node_cn` | Common Name of the Node | undefined |
| `icinga2_parent_cn` | Common Name of the parent Node | undefined |
| `icinga2_parent_address` | IP addresse or FQDN of the parent Node | undefined |
| `icinga2_ticket` | Request ticket | undefined |
| `icinga2_port` | Defines the port where Icinga is bound | 5665 |
| `icinga2_debian_version` | Defines Icinga version to be used for Debian | 2.9.1-1 |
| `icinga2_rhel_version` | Defines Icinga version to be used for RHEL | "2.10.1-1.el{{ ansible_distribution_major_version }}.icinga" |

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: 01.web.example.net
  vars:
    icinga2_node_cn: 01.web.example.net
    icinga2_parent_cn: icinga2.example.net
    icinga2_parent_address: 198.51.100.215
    icinga2_ticket: cf4ed9297b7a4c838ada1ba709e9befb1afa6526
  roles:
    - ansible-icinga2-daemon
```
Tested with the following Linux distributions
-------

- [X] Debian 9
- [ ] Debian 8
- [X] RHEL 7
- [X] RHEL 6

License
-------

GNU General Public License Version 2

Author Information
------------------

Spacial thanks to Valentino Gagliardi from the Icinga Dev Team. I used his [ansible role](https://github.com/Icinga/ansible-playbooks/tree/master/icinga2-ansible-no-ui) as a base.
