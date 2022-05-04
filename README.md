Role Name
=========

Installs and configures a hardened Minecraft 1.18.2 with Temurin OpenJDK 17 on Debian 11.

Install using [Ansible Galaxy](https://galaxy.ansible.com/):

```bash
ansible-galaxy install bsmirks.minecraft
```

Requirements
------------

1. Debian 11 server with at least the minimum server requirements to run Minecraft.
1. A user capable of running with priveliged access to the server.

I originally created this role with my own system in mind. Until I make the publickey authentication part of the OpenSSH config a reality, please ensure you have your SSH key on the host before running this.

Role Variables
--------------

Available variables and their default. More to be included soon for full configuration of the stack with Ansible.

* `backup_dir: /home/{{ mc_user }}/mcBackups` - the directory in which to place the server backups
* `enable_backups: true` - whether or not to enable server backups managed by this role
* `mc_user: floch` - the user that gets created on the server that operates the Minecraft application
* `java_home_value: /usr/lib/jvm/temurin-17-jdk-amd64` - `JAVA_HOME` environment variable
* `server_port: 26877` - the Minecraft server port to use
* `ssh_port: 2687` - the SSH port to use

Dependencies
------------

This list contains modules and/or roles that are not in the `ansible.builtin.*` namespace.

- [Ansible community UFW module](https://docs.ansible.com/ansible/latest/collections/community/general/ufw_module.html)

Example Playbook
----------------

```yaml
---
- hosts: foo.bar.com
  roles:
    - hardened_minecraft
  become: yes
```

License
-------

3-Clause BSD license

Author Information
------------------

Check out my [GitHub profile](https://github.com/bsmirks).
