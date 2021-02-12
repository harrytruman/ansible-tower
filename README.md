# Setup and Configure Ansible Tower for RHEL8

This repo will configure RHEL8 with Ansible 2.9, deploy Tower 3.7, and perform post-setup configuration of orgs/teams, projects, credentials, and job templates.

## Instructions:

1. Place your license file in `roles/config/files` (Tower 3.6 and earlier)

2. Be root or set your `ansible_become` in the inventory template, and run:

```
    ansible-playbook one-stop-shop.yml -e "sub_username=username" -e "sub_password=password"
```

### What does this role do?

#### Install Tower
- set timezone to utc
- register rhel
- add tower repo
- install pre-req yum packages
- place ssh keys on servers
- download, extract, and install tower

#### Configure Tower
- verify tower is up
- apply license
- install system pip packages
- install tower venv pip packages
- set ipv4 tcp keep alive
- adjust open file limits for tower

#### Add stuff to Tower
- add users
- create organizations
- add users to teams/orgs
- create inventory
- configure tower logging destination
- create fact collection project
- create linux root credential
- create fact collection job template
- launch fact collection job
- verify job completes
