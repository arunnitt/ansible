Kubernetes
==========

Install and configuring the Kubernetes Cluster on RHEL/CentOS and Ubuntu 20.04

- Install the necessary packages;
- Configure master server;
- Configure workers nodes.

Requirements
------------

- The SELinux and Firewall settings are not considered to be a concern of this role.

Role Variables
--------------

Variables that can be changed if you want

| Variables                                    | Defaults                      | Comments
| :---                                         | :---                          | :---                                                    
| `kubernetes_user`                            |                               | Kubernetes user administrator
|                                              |                               |
| `kubernetes_user_pass`                       |                               | Kubernetes user administrator password
|                                              |                               |
| `kubernetes_network`                         | weave                         | Pods Networking
|                                              |                               |


Variables that can be changed if you want.
For Red Hat family:

| Variables                                    | Defaults
|:---                                          |:---
| `kubernetes_url_repo`                        | Kubernetes Repository
|                                              |
| `kubernetes_url_key`                         | Kubernetes GPG Key
|                                              |
| `kubernetes_containerd`                      | Containerd Repository
|                                              |
| `kubernetes_pkg`                             | Kubernetes necessary packages
|                                              |
| `containerd_pkg`                             | Containerd necessary packages
|                                              |

Variables that can be changed if you want.
For Debian family:

| Variables                                    | Defaults
|:---                                          |:---
| `kubernetes_url_repo`                        | Kubernetes Repository
|                                              |
| `kubernetes_url_key`                         | Kubernetes GPG Key
|                                              |
| `containerd_url_key`                         | Containerd GPG Key
|                                              |
| `kubernetes_pkg`                             | Kubernetes necessary packages
|                                              |
| `containerd_pkg`                             | Containerd necessary packages
|                                              |

Dependencies
------------

No dependencies.


For correct operation, the playbook and inventory must be created as shown below.
---------------------------------------------------------------------------------

Playbook
=========
```
- hosts: kubernetes_masters,kubernetes_workers
  become: yes
  roles:
    - /path/acandid.kubernetes

```
Inventory
=========
```
[kubernetes_masters]
master_node01

[kubernetes_workers]
workers_node01
workers_node02
workers_node03
```

## Contributing

Issues, feature requests, ideas are appreciated and can be posted in the Issues section.


Author Information
------------------
LinkedIn: https://br.linkedin.com/in/almircandido/
