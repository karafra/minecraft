Role Name
=========

Installs and configures a hardened Minecraft 1.18.2 with Temurin OpenJDK 17 on Debian 11.

Requirements
------------

1. Debian 11 server with at least the minimum server requirements to run Minecraft.
1. A user capable of running with priveliged access to the server.

I originally created this role with my own system in mind. Until I make the publickey authentication part of the OpenSSH config a reality, please ensure you have your SSH key on the host before running this.

Role Variables
--------------

* `mcUser: floch` - the user that gets created on the server that operates the Minecraft application.
* `javaHomeValue: /usr/lib/jvm/temurin-17-jdk-amd64` - `JAVA_HOME` environment variable
* `serverPort: 26877` - The Minecraft server port to use
* `sshPort: 2687` - The SSH port to use

Dependencies
------------

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

bsmreker1@icloud.com
