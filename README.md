ovv.ftp
=======

[![Build Status](https://travis-ci.org/ovv/ansible-role-ftp.svg?branch=master)](https://travis-ci.org/ovv/ansible-role-ftp)

Ansible role to install and configure [ProFTPD](http://www.proftpd.org/).

Installation
------------

To install this roles clone it into your roles directory.

```bash
$ git clone https://github.com/ovv/ansible-role-ftp.git ovv.ftp
```

If your playbook already reside inside a git repository you can clone it by using git submodules.

```bash
$ git submodule add -b master https://github.com/ovv/ansible-role-ftp.git ovv.ftp
```

Role Variables
--------------

* `ftp_port`: Listening port of the FTP daemon (default to `21`).
* `ftp_users`: Dict of users allowed to connect vit FTP.
    * `password`: User password.
    * `home`: User home directory (default to `/home/{{ user }}`).
* `ftp_passive_ports`: FTP passive ports (omit by default).
* `ftp_masquerade_address`: Public address (omit by default).

Example Playbook
----------------

```yml
- hosts: localhost
  roles:
    - ovv.ftp
  vars:
    ftp_port: 2121
    ftp_passive_ports: 49000 50000
    ftp_masquerade_address: example.com
    ftp_users:
      example:
        password: pAssw0rd

```

License
-------

MIT
