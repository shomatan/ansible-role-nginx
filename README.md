Ansible role: nginx
=========

Installs and configures [Nginx](http://nginx.org/) Open Source HTTP and reverse proxy server.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: shomatan.nginx }
