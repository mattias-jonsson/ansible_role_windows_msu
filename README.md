Ansible Role: ansible_role_windows_msu
=========

Installs/Uninstalls Microsoft Update Standalone Packages from a list Microsoft Update Catalog URLs.

<ul>
<li>Windows Server
</ul>


Requirements
---------------

This role is dependent on the following Ansible collections:

`ansible.windows`, `community.windows`

None.

Role Variables
--------------

Available variables are listed below, along with default values where applicable (see `defaults/main.yml`):

| Variable | Required | Default | Comments |
| -------- | -------- | ------- | -------- |
| `ansible_role_windows_msu_updates` | Yes | | Contains a list of MSU URLs from the Microsoft Update Catalog to install/uninstall. The list contains a dict with `url` and `state`. See example playbook. |


Dependencies
------------

None.


Example Playbook
----------------


    - hosts: servers

      vars:
        ansible_role_windows_msu_updates:
          - url: https://catalog.s.download.windowsupdate.com/d/msdownload/update/software/updt/2023/02/windows10.0-kb5019181-x64_01173052877dc5762f73069a958c108afd1125be.msu
            state: absent
          - url: https://catalog.s.download.windowsupdate.com/c/msdownload/update/software/secu/2023/03/windows10.0-kb5023702-x64_25c0d04726b1f92c46e76d371ca58875051506c5.msu
            state: present


      roles:
         - ansible_role_windows_msu

License
-------

MIT

Author Information
------------------

Mattias Jonsson
