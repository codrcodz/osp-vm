Role Name
=========

Create a VM in OSP.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

group_vars

```
user_cert:
user_key:
user_cacert:
region:
auth_url:
username:
user_passwd:
osp_project:
server_name:
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
  vm:
    - vm1:
        action:
        server:
        image:      

    - vm2:
        action:
        server:
        image:

   - vm3:
       action:
       server:
       image:



Dependencies
------------


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
