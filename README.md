zabbix-agent
=========

[![Build Status](https://travis-ci.org/tenhishadow/zabbix-agent.svg?branch=master)](https://travis-ci.org/tenhishadow/zabbix-agent)

Role for installation and configuration management of zabbix agent service

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

### `firewalld`
- no by default 
- if true ansible will also manage firewalld by creating new service and allowing it on "firewalld_zone"

### `firewalld_zone`
- by default is "public"
- default zone for allowing zabbix agent service

### `zabbix_service_description`
- by default is "Zabbix agent service"
- just a description for firewalld service

### `zabbix_service_port`
- by default is "10050"
- default port tcp/10050 for zabbix agent service

User defined variables:
### `zabbix_agent_config`
- this variable is a hash
- must be defined before using!!!
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
