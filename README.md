# Ansible Tempest Remote
This repository holds playbook for deploying Openstack Tempest and Tempest Plugins\
onto the Undercloud of Openstack Hosts.\
I made it in order to automate the process of setting up Tempest and Tempest Plugins\
(from Upstream GIT Repositories).

It is also useful, to allow Remote Debugging, as it will setup ssh tunnel to the Undercloud\
(which is usually behind NAT).

Prior to the Tempest setup, it will create a virsh snapshot of the "clean" Undercloud vm.

To use it, you'll need to install Ansible first:
````
yum install ansible
````

After downloading Ansible-Tempest-Remote - make sure to modify the undercloud.inventory, with:

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
