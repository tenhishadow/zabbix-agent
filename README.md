zabbix-agent
=========

[![Build Status](https://travis-ci.org/tenhishadow/zabbix-agent.svg?branch=master)](https://travis-ci.org/tenhishadow/zabbix-agent)

Role for installation and configuration management of zabbix agent service

Requirements
------------

This role requires RHEL/CentOS 6/7 Linux distribution.


Role Variables
--------------

The role defines variables in `defaults/main.yml`:

### `zabbix_gpg_url`
- this variable is used to add gpg key while adding repo
  - default is "http://repo.zabbix.com/RPM-GPG-KEY-ZABBIX"
  - could be overriden in a playbook

### `zabbix_version`
- this variable is used to define zabbix version
  - default is "3.4"
  - could be overriden in a playbook

User defined variables:
### `zabbix_agent_config`
- this variable is a hash
- example is below

Dependencies
------------

-

Example Playbook
----------------

```yaml
---

- hosts: zabbix
  gather_facts: "false"
  vars:
    zabbix_agent_config:
      'Server=': "Server=mon.example.com"
      'Hostname=': "Hostname={{ inventory_hostname }}"
      'LogFile=': "LogFile=/dev/null"
  roles:
  - "tenhishadow.zabbix-agent"

...
```

License
-------

GPLv3

Author Information
------------------

Stanislav Cherkasov

adm@tenhi.ru
