# Ansible Smart Start in a Box

This repo will configure a complete Tower server/cluster that can be used both for customer demos and as a starting point for Ansible Smart Starts.

### Instructions:

  1. Setup your subs and repos.
  2. Add your license file to `roles/config/files`
  3. Run:
```
    ansible-playbook one-stop-shop.yml
```    
    or
```
    ansible-playbook tower-setup.yml
    ansible-playbook tower-admin.yml
    ansible-playbook tower-projects.yml
 ```

### What does this role do?

#### tower-setup.yml
- set timezone to utc
- install pre-req yum packages
- install tower-cli
- place ssh keys on servers
- download, extract, and install tower
- verify tower is up
- apply license
- install linux pip packages
- install tower venv pip packages
- set ipv4 tcp keep alive
- set open file limits for tower

#### tower-admin.yml
- add users
- create organizations
- add users to teams/orgs
- create inventory
- configure tower logging destination

#### tower-projects.yml
- create fact collection project
- create linux root credential
- create fact collection job template
- launch fact collection job
- verify job completes
