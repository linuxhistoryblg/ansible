ARCH_UPDATE
=========

Update Arch Linux Installed Packages

Example Playbook
----------------

Call the arch_update role from a playbook that looks like this:

```
---
- name: Update Arch Linux Installed Packages
  hosts: arch
  become: True
  roles:
    - linuxhistory.arch_update
```

License
-------

BSD

Author Information
------------------

Dan Davis, LinuxHistory.com