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
      volumes:
        - name: admin-test-06-storagevolume01
          size: 1
        - name: admin-test-06-bootvolume01
          size: 1
          image: cirros-0.3.5-x86_64-disk
      instances:
        - name: admin-test-05
          image: cirros-0.3.5-x86_64-disk               # What image name should be used to create the instance
          flavor: m1.tiny                               # What flavor name should be used to create the instance
          network: admin-private-network                # What private/tenant network the instance should be in
          security_groups:                              # What security groups the instance should be in
            - default
          #auto_ip: yes                                 # Auto give the instance a floating IP
          #key_name: test_key                           # User Public key to inject on vm creation
        - name: admin-test-06
          image: cirros-0.3.5-x86_64-disk
          flavor: m1.tiny
          network: admin-private-network
          security_groups:
            -default
          boot_from_volume: admin-test-06-bootvolume01
          attached_volumes:
            - admin-test-06-storagevolume01

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

