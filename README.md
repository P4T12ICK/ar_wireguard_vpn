wireguard_vpn
=========

Configure a client-to-server Wireguard VPN service and provision client config files.

Example Playbook
----------------

```yaml
- hosts: vpn
  roles:
    - role: p4t12ick.ar_wireguard_vpn
      vpn_physical_interface: ens5
      vpn_address: 10.0.1.10/24
      vpn_endpoint: 1.2.3.4
      vpn_clients:
        - name: client1
          address: 10.0.1.11/32
```

License
-------

Apache 2.0

Author Information
------------------

[P4T12ICK](https://github.com/P4T12ICK) 
