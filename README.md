## Ansible Role: Update
----------------------

[![CI](https://github.com/libert-xyz/ansible-role-update/workflows/CI/badge.svg?event=push)](https://github.com/libert-xyz/ansible-role-update/actions?query=workflow%3ACI)

Ansible role to Update/Upgrade linux packages for Linux machines.

## Requirements
------------

root access


## Role Variables
--------------

For APT (Debian) only: remove unused dependency packages

    update_autoremove: no

For APT (Debian) only: apt_upgrade type which can be: dist, full, yes, or safe

    update_upgrade_command: dist

For APT (Debian) only: update the apt cache if it's older than the cache_valid_time. Set in seconds.

    update_cache_valid_time: 300

When updating core libraries or services, a reboot may be required. Here you can select to:
 "yes": Always reboot when core libraries have changed.
 "no": Never reboot

    update_reboot: yes

## Dependencies
------------

None

## Example Playbook
----------------

    - hosts: servers
      become: true
      vars_files:
        - vars/main.yml
      roles:
        - libert_xyz.update

*Inside `vars/main.yml`*:

    update_reboot: no


## Compatibility
------------

This role has been tested on these [container images](https://hub.docker.com/u/libertxyz):

|container|tags|
|---------|----|
|centos7|latest|
|centos8|latest|
|amazonlinux2|latest|
|ubuntu18|latest|
|ubuntu20|latest|

## License
 -------

MIT

## Author Information
------------------

This role was created in 2021 by [Libert Schmidt](https://libert.xyz)