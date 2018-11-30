chris1984.motd
===============

An ansible role for configuring Message Of The Day (motd) file. By default this role adds additional information about the distro and the hardware.

Build Status
------------
[![Build Status](https://travis-ci.org/chris1984/motd.svg?branch=master)](https://travis-ci.org/chris1984/motd)

Requirements
------------

Tested on:

- RHEL 6.10 Santiago
- RHEL 7.6 Maipo

Should work with:

- All RHEL
- All Centos

Role Variables
--------------

```yaml
motd_sysadmins_signature: set sysadmin team signature
motd_sysadmins_email: set sysadmin support email
motd_content: set content of motd
motd_info: additional information to show in message
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
    - hosts: servers
      roles:
         - { role: chris1984.motd }
```

This playbook produces the /etc/motd file looking like this:

```bash
--------------------------------------------------------------------------
                    This system is managed by Ansible
--------------------------------------------------------------------------

This is host1 running Debian.

NOTE: System and application configuration for this host is managed by
Ansible Tower. To ensure that any changes you make here are not lost,
please contact with your system administrators.

 FQDN:    host1
 Distro:  RHEL 7.6 Maipo
 Virtual: NO
 CPUs:    8
 RAM:     16.0GB

Yours,
Random system administrators
email: random@random.com

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

Last ansible run: 2018-11-30T23:09:07Z
```

License
-------

MIT License.

Author Information
------------------

- Chris Roberts - chrobert@redhat.com - https://www.linkedin.com/in/croberts84/
- Work at Redhat on the Foreman/Katello projects and also maintain fog-vsphere.
