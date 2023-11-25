Role Name
=========

Arch Linux Post Configuration
  - This role takes a fresh installation of Arch Linux and runs the following post-configuration tasks:
      - Update package cache
      - Upgrade all packages
      - Install Wayland 
      - Install and configure the Sway Window Manager
      - Install and configure the Waybar status bar for Wayland
      - Install and configure the Wofi application picker


Requirements
------------

Successful execution of this role requires:
  - The `community.general.pacman` module from the `community.general` collection.
  - A user capable of escalating to root via sudo on the target Arch Linux host.

Role Variables
--------------

This role configures the Sway WM for a single user on the target system. If that user does not exist, one will be created. The variables used to create the user are:
  - default_username   # the username of the user
  - default_password   # password for the default_username account. This value should be vaulted for security!!! 

Place `default_username` into this role's vars/ directory, at the host or group vars level, or in the site.yml demonstrated below and vault `default_password`. A non-vaulted example is available in this role's defaults/ directory.

Dependencies
------------

  - The community.general collection

Example Playbook
----------------

Call the linuxhistory.arch_postconf role in a playbook like this:

    ---
    - name: Call Arch Post Provisioning Role
      hosts: arch
      vars:
        default_username: yourusername
      become: True
      tasks:
      - name: Include the linuxhistory.arch_postconf role
        include_role: 
          name: linuxhistory.arch_postconf

License
-------

BSD

Author Information
------------------

Dan Davis, linuxhistory.com