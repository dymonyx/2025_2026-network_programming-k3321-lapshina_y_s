setup_chr
=========

An Ansible role for configuring MikroTik Cloud Hosted Router (CHR) with core networking services.

Description
-----------

This role automates the configuration of CHR routers, including:
- User credentials setup (login and password)
- NTP configuration for time synchronization
- OSPF routing protocol setup

Requirements
------------

- Ansible >= 2.1
- SSH access to MikroTik CHR router with administrative privileges
- `community.routeros` module (for MikroTik configuration management)

Role Variables
--------------

Default values are located in `defaults/main.yml` and `vars/main.yml`. Key variables:

- `inventory_hostname` - hostname of the CHR router (default: `router1`)
- `ansible_host` - IP address of the CHR router (default: `192.168.1.1`)
- `ntp_server` - IP address of NTP server for time synchronization
- `ospf_neighbor` - IP address of OSPF neighbor used in `/routing ospf static-neighbor` on `wireguard1` (example: `192.168.100.2`)

Example Playbook
----------------

```yaml
- hosts: chr_routers
  roles:
    - setup_chr
```

Author
------

Lapshina Yulia

License
-------

Apache-2.0
