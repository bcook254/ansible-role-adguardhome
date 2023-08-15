Ansible Role: adguardhome
=========

Installs AdGuardHome on Linux machines.

Versioning Policy
-----------------
Each minor version of this role is designed to be compatible with the corresponding patch release of `AdGuardHome`. For example, version `107.36.x` is compatible with `AdGuardHome` version `0.107.36`. This is due to breaking changes introduced in the settings file and allows for bug fix releases in the role between updates.

Install
-------
Using ansible galaxy

`ansible-galaxy install bcook254.adguardhome>=107.36,<107.37`

Requirements
------------

Permission to:
  - Create or modify users/groups
  - Create or modify required directories

Role Variables
--------------
A non-exhuastive list of available variables is listed below, along with their default vaules. For a list of variables available for the AdguardHome configuration file please see `templates/AdGuardHome-{{ adguardhome_template_version }}.yaml.j2`.

    adguardhome_version: 0.107.36

The version of AdGuardHome to be installed.

    adguardhome_user: adguardhome
    adguardhome_group: adguardhome

The user and group that will be created and AdGuardHome will run under.

    adguardhome_daemon: adguardhome

The name of the service used to control the AdGuardHome process.

    adguardhome_home_dir: /var/lib/adguardhome
    adguardhome_data_dir: "{{ adguardhome_home_dir }}"
    adguardhome_bin_dir: /usr/local/bin
    adguardhome_config_dir: /etc/adguardhome

Default folders created for AdguardHome binaries and data.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: bcook254.adguardhome
           become: yes

License
-------

MIT / BSD

Author Information
------------------

This role was created by Benjamin Cook.
