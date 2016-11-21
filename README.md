# Ansible role: nginx
Installs and configures [Nginx](http://nginx.org/) Open Source HTTP and reverse proxy server.

## Requirements
None.

## Role Variables
|Key|Type|Description|Default|
|:--|:---|:----------|:------|
|nginx_loglotate_create|String||0640 nginx nginx|

## Dependencies
None.

## Example playbook

```yaml
- hosts: all
  roles:
    - { role: nginx }
  vars:

```
