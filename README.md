# Ansible Network Collection for Dell EMC OS9

## Collection contents
The OS9 Ansible Network Collection includes the Ansible modules, plugins and roles required to work on a Dell EMC OS9 PowerSwitch. It also includes sample playbooks and documents that illustrate how the collection can be used.

### Ansible modules
The following Ansible modules are part of the OS9 collection:

- **os9_command.py** — Run commands on remote devices running Dell EMC OS9

- **os9_config.py** — Manage configuration sections on remote devices running Dell EMC OS9
  
- **os9_facts.py** — Collect facts from remote devices running Dell EMC OS9

### Ansible roles
The roles facilitate provisioning of device running Dell EMC OS9. Some of the roles included in the collection are os9_aaa , os9_bgp, os9_ecmp, and so on. The docs directory in the collection includes documentation for each of the roles part of the collection.

### Playbooks
The playbooks directory includes sample playbooks that illustrate the usage of OS9 collections for provisioning device running Dell EMC OS9.

## Collection Installation
Install the latest version of OS9 collection from Ansible Galaxy:

    ansible-galaxy collection install dellemc.os9

To install a specific version, a version range identifier must be specified. For example, to install the most recent version that is greater than or equal to 1.0.0 and less than 2.0.0:

    ansible-galaxy collection install 'dellemc.os10:>=1.0.0,<2.0.0'

## Sample playbook

    - hosts: os9_sw1
      connection: network_cli
      collections:
        - dellemc.os9
      roles:
        - os9_vlan

> **NOTE**: The environment variable ANSIBLE_NETWORK_GROUP_MODULES should be set to 'os9' for using os9-collections in the playbook.

## Sample host_vars/os9_sw1.yaml

    hostname: os9_sw1
    # parameters for connection type network_cli
    ansible_ssh_user: xxxx
    ansible_ssh_pass: xxxx
    ansible_network_os: dellemc.os9.os9

## Sample inventory.yaml

    [os9]
    os9_sw1 ansible_host=100.104.28.119
