# Ansible Smart Start in a Box

This repo will configure a complete Tower server/cluster that can be used for getting started with Ansible 2.9 and Tower 3.6, and as the logging source for ELK.

### Instructions:

Place your license file in `roles/config/files`.

Be root, or set your `ansible_become` in the inventory template.

```
    ansible-playbook one-stop-shop.yml -e "sub_username=username" -e "sub_password=password"
```

### What does this role do?

#### Install Tower
- set timezone to utc
- subscribe to red hat
- subscribe to tower repo
- install pre-req yum packages
- place ssh keys on servers
- download, extract, and install tower

#### Configure Tower
- verify tower is up
- apply license
- install linux pip packages
- install tower venv pip packages
- set ipv4 tcp keep alive
- set open file limits for tower

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
