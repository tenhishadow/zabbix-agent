tenhishadow.zabbix_agent
=========

[![Build Status](https://travis-ci.org/tenhishadow/zabbix-agent.svg?branch=master)](https://travis-ci.org/tenhishadow/zabbix-agent)

Role for installation and configuration management of  zabbix agent service

Role Variables
--------------

just take a look at defaults.yml

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

```yaml
- hosts: all
  gather_facts: yes
  vars:
    zabbix_agent_config:
      Server: "mon.example.com"
      Hostname: "hostname1"
  roles:
  - "tenhishadow.zabbix_agent"
...
```

License
-------

GPLv3

Author Information
------------------
* **[Stanislav Cherkasov](mailto:adm@tenhi.ru)** - [github](https://github.com/tenhishadow)
