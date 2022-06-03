# ansible-wazuh-agent

[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen?style=flat)](https://opensource.org/licenses/Apache-2.0)

This role is used for installing and configuring the Wazuh client on Ubuntu and RedHat based operating systems.

Restrictions for this library are in:

* CentOS 7 or Rocky Linux 8
* Ubuntu distribution, recommended versions above 18.04

This role was developed following the instructions available on the Wazuh

https://documentation.wazuh.com/current/installation-guide/wazuh-agent/index.html

And using the role as a base

https://github.com/lotusnoir/ansible-apps_wazuh_agent

## Role Variables (default values)

```yaml
wazuh_version: "4.x"
wazuh_manager_ip: ""
wazuh_manager_port: "1514"
wazuh_registration_port: "1515"
wazuh_manager_protocol: "tcp"
wazuh_agent_group: "server-linux"
wazuh_registration_password: ""
```

### Example Playbook

```yaml
- name: Install and Configure Wazuh Agent
  hosts: all
  roles:
    - role: "ansible-wazuh-agent"
  vars:
    - wazuh_manager_ip: "127.0.0.1"
    - wazuh_registration_password: "XXXXXXXXXXXXX"
```

## To run tests on molecule

Packages needed to install

* molecule
* molecule-docker
* molecule-goss

Run the commands to install

```
pip install molecule
pip install molecule-docker
pip install molecule-goss
```

To run the test run the command below

```
molecule test
```