minecraft
=========

An Ansible role for installing and configuring Minecraft server 1.18.2 using Temurin 17 OpenJDK on Debian.

Install using [Ansible Galaxy](https://galaxy.ansible.com/):

```bash
ansible-galaxy install bsmirks.minecraft
```

Requirements
------------

1. Debian 11 server with at least the minimum server requirements to run Minecraft.
1. A user capable of running with priveliged access to the server.

Role Variables
--------------

All available variables for this role can be found in [defaults/main.yml](defaults/main.yml).

Example Playbook
----------------

```yaml
---
- hosts: foo.bar.com
  become: yes
  roles:
    - role: bsmirks.minecraft
      vars:
        backup_retention: 7
        difficulty: easy
        level_name: myWorld
        motd: Welcome to your doom, peasant!
        server_port: 25565
```

License
-------

3-Clause BSD license

Author Information
------------------

Check out my [GitHub profile](https://github.com/bsmirks).
