# Ansible Network Collection for Dell EMC OS9

## Collection contents
The collection includes the Ansible modules, plugins and roles required to work on a Dell EMC OS9. It also includes sample playbooks and documents that illustrate how the collection can be used.

### Ansible modules

- **os9_command.py** — Run commands on remote devices running Dell EMC OS9

- **os9_config.py** — Manage configuration sections on remote devices running Dell EMC OS9
  
- **os9_facts.py** — Collect facts from remote devices running Dell EMC OS9

### Ansible roles
Roles facilitate provisioning of device running Dell EMC OS9. These roles explain how to use OS9 and include **os9_aaa** , **os9_bgp**, **os9_ecmp**, and so on. There are over 22 roles available. The documentation for each role is at [OS9 roles documentation](https://github.com/ansible-collections/dellemc.os9/blob/master/docs/roles.rst)

### Playbooks
Sample playbooks are included for provisioning devices running Dell EMC OS9.

- [CLOS Fabric](https://github.com/ansible-collections/dellemc.os9/blob/master/playbooks/clos_fabric_ebgp/README.md) — Example playbook to build CLOS Fabric with Dell EMC OS9 switches

## Installation
Use this command to install the latest version of the OS9 collection from Ansible Galaxy:

    ansible-galaxy collection install dellemc.os9

To install a specific version, a version range identifier must be specified. For example, to install the most recent version that is greater than or equal to 1.0.0 and less than 2.0.0:

    ansible-galaxy collection install 'dellemc.os9:>=1.0.0,<2.0.0'

## Dependency
Ansible version **2.10 or later**

> **NOTE**: For Ansible version lower than 2.10, Please use [dellos9 modules](https://ansible-dellos-docs.readthedocs.io/en/latest/modules.html#os9-modules) and [dellos roles](https://ansible-dellos-docs.readthedocs.io/en/latest/roles.html)

## Sample playbook

    - hosts: os9_sw1
      connection: network_cli
      collections:
        - dellemc.os9
      roles:
        - os9_vlan

## Sample host_vars/os9_sw1.yaml

    hostname: os9_sw1
    # parameters for connection type network_cli
    ansible_ssh_user: xxxx
    ansible_ssh_pass: xxxx
    ansible_network_os: dellemc.os9.os9

## Sample inventory.yaml

    [os9]
    os9_sw1 ansible_host=100.104.28.119

(c) 2020 Dell Inc. or its subsidiaries. All rights reserved.
