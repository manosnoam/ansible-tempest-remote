# Ansible Tempest Remote
This repository holds an Ansible playbook for deploying [Openstack Tempest](https://docs.openstack.org/tempest/latest) and [Tempest Plugins](https://docs.openstack.org/tempest/latest/plugin-registry.html)\
onto the [Undercloud of Red Hat OpenStack Platform](https://redhatstackblog.redhat.com/tag/undercloud).

I made it in order to automate the process of setting up Tempest and required Plugins (from upstream GIT Repositories),
which are the common testing suite for Openstack projects. 

One usecase of this script, is to allow [Python Remote Debugging](https://www.jetbrains.com/help/pycharm/remote-debugging-with-product.html) of the Tempest code - since the playbook will setup an SSH tunnel to the Undercloud (which is probably residing behind NAT).

Prior to the Tempest setup, it will also create a virt snapshot of the current Undercloud instance, in case you'd like to revert later.

## Installing
In order to run this Ansible playbook, first install Ansible:
````
yum install ansible
````

**The minimum required version of Ansible for the playbooks >= 2.4**

After downloading/cloning Ansible-Tempest-Remote - please make sure to modify the undercloud.inventory, with:

- The required Openstack hostname (which holds the Undercloud).
- The required Tempest plugins (URLs of Git repositories).

## Running
To run the playbook on all of the defined hosts of undercloud.inventory:
````
ansible-playbook playbooks/remote-debug-tempest.yml
````

It is recommended to initially test the playbook in "dry-run" mode: `--check`, and also use verbosity: `-v`.


To run on a specific host (that was pre-defined in undercloud.inventory, e.g. "titan13"):
````
ansible-playbook playbooks/remote-debug-tempest.yml -e "hostname=titan13"
````

![](resources/ansible-tempest-remote.gif)

For any question, feel free to contact me - nmanos@redhat.com
