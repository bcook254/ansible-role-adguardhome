Ansible Role: adguardhome
=========

Installs AdGuardHome on Linux machines.

Versioning Policy
-----------------
Each minor version of this role is designed to be compatible with the corresponding patch release of `AdGuardHome`. For example, version `107.55.x` is compatible with `AdGuardHome` version `0.107.55`. This is due to breaking changes introduced in the settings file and allows for bug fix releases in the role between updates.

Install
-------
Using ansible galaxy

`ansible-galaxy install bcook254.adguardhome>=107.55,<107.56`

Requirements
------------

Permission to:
  - Create or modify users/groups
  - Create or modify required directories

Role Variables
--------------
A non-exhuastive list of available variables is listed below, along with their default vaules. For a list of variables available for the AdguardHome configuration file, please see `defaults/main.yml`.

    adguardhome_version: 0.107.55

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

    adguardhome_bin_file: "{{ adguardhome_bin_dir }}/AdGuardHome"
    adguardhome_config_file: "{{ adguardhome_config_dir }}/AdGuardHome"

Default file names for the AdguardHome binary and config file.

    adguardhome_download_uri:

Optional URI that will override the default AdGuardHome URL constructed by this role. The URI must point to a tarball that has the same structure as the official AdGuardHome release files. If it is a file location, the file must already exist on the remote machine. This is only necessary for custom/local builds or architectures this role does not yet properly detect.

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
