Arch Optimize Mirrorlist
=========

Arch Linux's package manager, pacman, pulls packaged software installations and updates from known repositories listed in /etc/pacman.d/mirrorlist. The observed performance between pacman and the repository is a function of your geographical distance from a given mirror, the network speed between you and the mirror, and the available bandwidth of the mirror itself. This role takes a large master mirrorlist and configures pacman to use the 3 fastest mirrors available from the master list at the time the role is called.

Requirements
------------

To successfully call this role you will first need to retrieve a master mirror list from the [Pacman Mirrorlist Generator](https://archlinux.org/mirrorlist/).

Copy the output of this tool to a file named mirrorlist and place the file in the templates directory of this role.

Role Variables
--------------

none

Dependencies
------------

none

Example Playbook
----------------

Call the role from a playbook that looks like this:
```
---
- name: Update Mirror List Based on Speed Ranking
  hosts: arch
  roles:
    - linuxhistory.arch_optimize_mirrorlist 
```

License
-------

BSD

Author Information
------------------

Dan Davis, LinuxHistory.com

