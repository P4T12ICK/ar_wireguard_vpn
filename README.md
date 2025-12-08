wireguard_vpn
=========

Configure a client-to-server Wireguard VPN service and provision client config files.

The role supports different actions via the `wireguard_action` variable:
- `deploy` (default): Deploy and configure the WireGuard server, generate keys, and create client config files
- `get_config`: Retrieve and display existing client configuration files

Example Playbooks
-----------------

### Deploy WireGuard Server (Default)

```yaml
- hosts: vpn
  roles:
    - role: p4t12ick.ar_wireguard_vpn
      wireguard_action: deploy  # This is the default, can be omitted
      vpn_physical_interface: ens5
      vpn_address: 10.0.1.10/24
      vpn_endpoint: 1.2.3.4
      vpn_clients:
        - name: client1
          address: 10.0.1.11/32
        - name: client2
          address: 10.0.1.12/32
```

### Get Client Configurations

Retrieve and display existing client configuration files without deploying:

```yaml
- hosts: vpn
  roles:
    - role: p4t12ick.ar_wireguard_vpn
      wireguard_action: get_config
      vpn_clients_dir: /etc/wireguard
      vpn_clients:
        - name: client1
        - name: client2
```

License
-------

Apache 2.0

Author Information
------------------

[P4T12ICK](https://github.com/P4T12ICK) 
