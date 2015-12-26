ansible-ethercalc
===========================

Install and maintain an [Ethercalc](https://ethercalc.net/) service.

This role will setup an ethercalc service running on 0.0.0.0:8000.

You need to have a running webserver with a vhost pointing to your ethercalc instance and it's port. 

All spreadsheets will expire after 30days of inactivity

Role Variables
--------------

* `ethercalc_required_packages: [ odejs, npm, git, make, g++, ]`
* `ethercalc_repository: "https://github.com/audreyt/ethercalc.git"`
* `ethercalc_repository_key_file: ""`
* `ethercalc_repository_version: "master"`
* `ethercalc_user: "ethercalc"`
* `ethercalc_group: "{{ ethercalc_user }}"`
* `ethercalc_home: "/home/ethercalc"`
* `ethercalc_path: "{{ ethercalc_home }}/ethercalc"`
* `ethercalc_title: "Ethercalc"`
* `ethercalc_ip: 0.0.0.0`
* `ethercalc_port: 8000`
* `ethercalc_monit_enabled: False`
* `ethercalc_spread_seconds_to_expire: 2592000`


Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: shadow.ethercalc }

License
-------

GPLv3

Author Information
------------------

https://www.systemli.org
