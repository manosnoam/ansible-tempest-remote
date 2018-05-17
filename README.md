# Ansible Tempest Remote
Ansible-Tempest-Remote repository holds playbook for deploying Openstack Tempest and Tempest Plugins onto the Undercloud of Openstack Hosts.
I made it in order to automate the process of setting up Tempest and Tempest Plugins (from Upstream GIT Repositories).
It is also useful, to allow Remote Debugging, as it will setup ssh tunnel to the Undercloud (which is usually behind NAT).

## Documentation
* [TODO]

**The minimum required version of Ansible for the playbooks >= 2.4**

## Playbooks and Roles
* [TODO]

## Note
Please modify the undercloud.inventory, before running the playbook, \
with the required Openstack hosts (which holds the Undercloud), and with required Tempest Git Repositories.


```
ansible-playbook playbooks/remote-debug-tempest.yml -i environments/undercloud.inventory -v
```

For any question, feel free to contact me - nmanos@redhat.com
