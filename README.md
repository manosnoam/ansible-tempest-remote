# Ansible Tempest Remote
This repository holds an Ansible playbook for deploying [Openstack Tempest](https://docs.openstack.org/tempest/latest) and [Tempest Plugins](https://docs.openstack.org/tempest/latest/plugin-registry.html)\
onto the [Undercloud of Red Hat OpenStack Platform](https://redhatstackblog.redhat.com/tag/undercloud).

I made it in order to automate the process of setting up Tempest and required Plugins (from upstream GIT Repositories),
which are the common testing suite for Openstack projects. 

A good usage of it, is to allow [Python Remote Debugging](https://www.jetbrains.com/help/pycharm/remote-debugging-with-product.html) of the Tempest code - since the playbook will setup an SSH tunnel to the Undercloud (which is probably residing behind NAT).

Prior to the Tempest setup, it will also create a virsh snapshot of the current Undercloud instance, in case you'd like to revert later.

To run Ansible playbook, first install Ansible:
````
yum install ansible
````

After downloading/cloning Ansible-Tempest-Remote - please make sure to modify the undercloud.inventory, with:

- The required Openstack hostname (which holds the Undercloud).
- The required Tempest plugins (URLs of Git repositories).


To run the playbook:
````
ansible-playbook playbooks/remote-debug-tempest.yml -i environments/undercloud.inventory -v
````

## Documentation
* [TODO]

**The minimum required version of Ansible for the playbooks >= 2.4**

## Playbooks and Roles
* [TODO]


For any question, feel free to contact me - nmanos@redhat.com
