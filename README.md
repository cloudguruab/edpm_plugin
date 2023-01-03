# EDPM Plugin Support
- Goal of this repo is to showcase the possibility of outputting contents from a inventory yaml/env variable to organize ansible inventory. 

### Steps
- Installing via ansible collection

```bash
ansible-galaxy collection install cloudguruab.edpm_plugin
```

- Set plugin location for ansible 

```bash
export ANSIBLE_INVENTORY_PLUGINS=dirpath
```

- Executing the plugin

```bash
ansible-inventory -i inventory.yaml --list
ansible-inventory -i inventory.yaml --graph
ansible-playbook -i inventory.yaml --playbook-dirs ./playbookname.yaml
```

- Example output given the base edpm_inventory.yaml file:

```bash
{
    "_meta": {
        "hostvars": {
            "192.168.122.139": {
                "chrony_ntp_servers": [
                    "clock.redhat.com",
                    "clock2.redhat.com"
                ],
                "ctlplane_dns_nameservers": [
                    "192.168.122.1"
                ],
                "ctlplane_gateway_ip": "192.168.122.1",
                "ctlplane_subnet_cidr": 24,
                "dns_search_domains": [],
                "neutron_physical_bridge_name": "br-ex",
                "neutron_public_interface_name": "eth0",
                "service_net_map": {
                    "nova_api_network": "internal_api",
                    "nova_libvirt_network": "internal_api"
                },
                "tripleo_network_config_hide_sensitive_logs": false,
                "tripleo_network_config_template": "templates/net_config_bridge.j2",
                "tripleo_nodes_validation_validate_controllers_icmp": false,
                "tripleo_nodes_validation_validate_gateway_icmp": false,
                "tripleo_nova_compute_DEFAULT_transport_url": "rabbit://guest:ar3TXOAYMaznW29fRLj2ILXKs@standalone.ctlplane.localdomain:5672/?ssl=0",
                "tripleo_nova_compute_cache_memcache_servers": "standalone.ctlplane.localdomain:11211",
                "tripleo_nova_compute_cinder_auth_url": "http://192.168.24.3:5000/v3",
                "tripleo_nova_compute_cinder_password": "ip3VDO3mq6JObAQqfekzt85kp",
                "tripleo_nova_compute_config_overrides": {
                    "DEFAULT": {
                        "oslo_messaging_notifications_transport_url": "rabbit://guest:ar3TXOAYMaznW29fRLj2ILXKs@standalone.ctlplane.localdomain:5672/?ssl=0",
                        "transport_url": "rabbit://guest:ar3TXOAYMaznW29fRLj2ILXKs@standalone.ctlplane.localdomain:5672/?ssl=0"
                    },
                    "cache": {
                        "memcache_servers": "standalone.ctlplane.localdomain:11211"
                    },
                    "cinder": {
                        "auth_url": "http://192.168.24.3:5000/v3",
                        "password": "ip3VDO3mq6JObAQqfekzt85kp"
                    },
                    "neutron": {
                        "auth_type": "v3password",
                        "auth_url": "http://192.168.24.3:5000/v3",
                        "password": "viaNg9cyAqS8N1ydQe7n3XkuM",
                        "project_domain_name": "Default",
                        "project_name": "service",
                        "region_name": "regionOne",
                        "user_domain_name": "Default",
                        "username": "neutron"
                    },
                    "placement": {
                        "auth_type": "password",
                        "auth_url": "http://192.168.24.3:5000",
                        "password": "Tnqq58zC6mD9O2jaC8xfiyt3M",
                        "project_domain_name": "Default",
                        "project_name": "service",
                        "region_name": "regionOne",
                        "user_domain_name": "Default",
                        "username": "placement",
                        "valid_interfaces": "internal"
                    },
                    "service_user": {
                        "auth_type": "password",
                        "auth_url": "http://192.168.24.3:5000",
                        "password": "59CnvTwMZcJfxCF9NU8bGWrcd",
                        "project_domain_name": "Default",
                        "project_name": "service",
                        "region_name": "regionOne",
                        "send_service_user_token": "True",
                        "user_domain_name": "Default",
                        "username": "nova"
                    },
                    "vnc": {
                        "novncproxy_base_url": "http://192.168.24.3:6080"
                    }
                },
                "tripleo_nova_compute_neutron_auth_type": "v3password",
                "tripleo_nova_compute_neutron_auth_url": "http://192.168.24.3:5000/v3",
                "tripleo_nova_compute_neutron_password": "viaNg9cyAqS8N1ydQe7n3XkuM",
                "tripleo_nova_compute_neutron_project_domain_name": "Default",
                "tripleo_nova_compute_neutron_project_name": "service",
                "tripleo_nova_compute_neutron_region_name": "regionOne",
                "tripleo_nova_compute_neutron_user_domain_name": "Default",
                "tripleo_nova_compute_neutron_username": "neutron",
                "tripleo_nova_compute_oslo_messaging_notifications_transport_url": "rabbit://guest:ar3TXOAYMaznW29fRLj2ILXKs@standalone.ctlplane.localdomain:5672/?ssl=0",
                "tripleo_nova_compute_placement_auth_type": "password",
                "tripleo_nova_compute_placement_auth_url": "http://192.168.24.3:5000",
                "tripleo_nova_compute_placement_password": "Tnqq58zC6mD9O2jaC8xfiyt3M",
                "tripleo_nova_compute_placement_project_domain_name": "Default",
                "tripleo_nova_compute_placement_project_name": "service",
                "tripleo_nova_compute_placement_region_name": "regionOne",
                "tripleo_nova_compute_placement_user_domain_name": "Default",
                "tripleo_nova_compute_placement_username": "placement",
                "tripleo_nova_compute_placement_valid_interfaces": "internal",
                "tripleo_nova_compute_service_user_auth_type": "password",
                "tripleo_nova_compute_service_user_auth_url": "http://192.168.24.3:5000",
                "tripleo_nova_compute_service_user_password": "59CnvTwMZcJfxCF9NU8bGWrcd",
                "tripleo_nova_compute_service_user_project_domain_name": "Default",
                "tripleo_nova_compute_service_user_project_name": "service",
                "tripleo_nova_compute_service_user_region_name": "regionOne",
                "tripleo_nova_compute_service_user_send_service_user_token": true,
                "tripleo_nova_compute_service_user_user_domain_name": "Default",
                "tripleo_nova_compute_service_user_username": "nova",
                "tripleo_nova_compute_vnc_novncproxy_base_url": "http://192.168.24.3:6080",
                "tripleo_ovn_dbs": [
                    "192.168.24.1"
                ],
                "vars": {
                    "ansible_ssh_user": "root",
                    "ctlplane_ip": "192.168.24.100",
                    "fqdn_internal_api": "{{ ansible_fqdn }}",
                    "internal_api_ip": "192.168.24.2",
                    "tenant_ip": "192.168.24.2"
                }
            }
        }
    },
    "all": {
        "children": [
            "compute",
            "ungrouped"
        ]
    },
    "compute": {
        "hosts": [
            "192.168.122.139"
        ]
    }
}
```