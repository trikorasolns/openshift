Role Name
=========

Manages shares on RedHat OpenStack Platform.

Requirements
------------

**Ansible Collection requirements**

* openstack.cloud >= 2.5.0

Other requirements.

* Connection to RHOSP

Role Variables
--------------

| Variable  | Comments |
| ------------- | ------------- |
| rhosp_share_manage_instance_list <br/> <span style="color:magenta">list</span> / <span style="color:red">required</span> | List of instance private IPs that will be authorized to use the share. |
| rhosp_share_manage_name<br/><span style="color:magenta">string</span> / <span style="color:red">required</span> | Name of the share to be created. |
| rhosp_share_manage_network_name<br/><span style="color:magenta">string</span> / <span style="color:red">required</span> | Name of the Share network to be used.<br/>The network will be created, and associated to the Neutron network, if it doesn't exist. |
| rhosp_share_manage_neutron_network<br/><span style="color:magenta">string</span> | Name of the Neutron network the share network will be associated to.<br/><span style="color:red">Required</span> if the Share network doesn't exist and is to be created, otherwise it won't be used. |
| rhosp_share_manage_protocol<br/><span style="color:magenta">string</span> / <span style="color:red">required</span> | Share protocol. The value is dependent of the OpenStack implementation. <br/>As of the OpenStack documentation posible values are: <ul> <li>NFS</li> <li>CIFS</li> <li>CephFS</li> <li>GlusterFS</li> <li>HDFS</li> </ul> |
| rhosp_share_manage_region<br/><span style="color:magenta">string</span> / <span style="color:red">required</span> | OpenStack region. |
| rhosp_share_manage_size<br/><span style="color:magenta">int</span> / <span style="color:red">required</span> | Share size in GiB. |
| rhosp_share_manage_type<br/><span style="color:magenta">string</span> / <span style="color:red">required</span> | OpenStack Share Type<br/>List available through `openstack share type list`  |
| state<br/><span style="color:magenta">string</span> | If `present` the share will be created. <br/> If `absent` the share will be removed.<br/>**Choices**:<ul><li>`absent`</li><li><span style="color:blue">`present` <- (default)</span></li></ul> |



Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

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
