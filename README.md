Role Name
=========

Create a VM in OSP.
Module Docs http://docs.ansible.com/ansible/latest/os_server_module.html
http://docs.ansible.com/ansible/latest/os_server_action_module.html


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
      user_domain_name: "Default"
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
      flavor: m1.tiny            # Instance Flavor
      region_name: "RegionOne"   # What Region
      availability_zone: nova    # What zone to use
      state: present             # If the VM is there
      network: public            # What network to be in
      security_groups: default   # What security group to use
      auto_ip: yes               # Auto give the instance a floating IP
      action: rebuild            # action to take against the server
      server: hadoop-01          # the name of the server the action will be taken against on. Can use wildcards. This can be used to list a number of servers that the action will be taken. For example, if you want to stop 200 servers because you are done with testing or rebuild them to deploy the new code.
      rpms:
        - python-pip
        - vim-common
        - ruby
        - python3
      pip:
        - virtualenv
      ruby_gems:
        - chef
        - rbenv
      virtualenvs:
      - venv1:
        path: /root/venv1
        packages:
          - ansible
          - requests
      - venv2
        path: /home/mike/venv2
        packages:
          - fabric


    other_vm:
      name:
      image:
      key_name:
      flavor:
      region_name:
      availability_zone:
      security_groups:
      auto_ip:
      action:
      server:

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

