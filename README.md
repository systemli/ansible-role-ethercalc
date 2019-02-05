ansible-ethercalc
=================

[![Build Status](https://travis-ci.org/systemli/ansible-role-ethercalc.svg)](https://travis-ci.org/systemli/ansible-role-ethercalc) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-ethercalc-blue.svg)](https://galaxy.ansible.com/detail#/role/6657)

Install and maintain an [Ethercalc](https://ethercalc.net/) service.

This role will setup an ethercalc service running on 0.0.0.0:8000.

You need to have a running webserver with a vhost pointing to your ethercalc instance and it's port. 

All spreadsheets will expire after 30days of inactivity

Role Variables
--------------

* `ethercalc_required_packages: [ git ]`
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

Download
--------

Download latest release with `ansible-galaxy`

	ansible-galaxy install systemli.ethercalc

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: systemli.ethercalc }

Testing & Development
---------------------

Tests
-----

For developing and testing the role we use Travis CI, Molecule and Vagrant. On the local environment you can easily test the role with

Run local tests with:

```
molecule test 
```

Requires Molecule, Vagrant and `python-vagrant` to be installed.For developing and testing the role we use Travis CI, Molecule and Vagrant. On the local environment you can easily test the role with

License
-------

GPLv3

Author Information
------------------

https://www.systemli.org
