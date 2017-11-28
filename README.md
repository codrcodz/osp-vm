Role Name
=========

Create a VM in OSP.
Module Docs http://docs.ansible.com/ansible/latest/os_server_module.html


Requirements
------------


Role Variables
--------------
```

osp_vm:
  api:
    auth:
      auth_url: "http://192.168.0.1:35357/v.20"
      username: "admin"
      password: "{{ keystone_admin_password }}"
      project_name: "admin"
    auth_type: "password"
    endpoint_type: "admin"
    region_name: "RegionOne"
    keystone_version: "2"
    projecT_name: "admin"
  vm:
    test:
      name: test                 # Name of the Instance
      image: hadoop              # Name or ID of the Image
      key_name: test_key         # User Key Pair
      flavor: 101                # Instance Flavor
      region_name: region1       # What Region
      availability_zone: zone1   # What zone to use
      security_groups: hadoop    # What security group to use
      auto_ip: yes               # Auto give the instance a floating IP

    other_vm:
      name:
      image:
      key_name:
      flavor:
      region_name:
      availability_zone:
      security_groups:
      auto_ip:

```
Dependencies
------------


Example Playbook
----------------

  - hosts: all
    role:
      - osp-vm 


License
-------

BSD

Author Information
------------------

