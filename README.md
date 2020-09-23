# Deploy stack elk with provisioning docker swarm

- ansible-files: config server and deployment stack over docker swarm
- stack-yml: docker swarm yml files

## Requirements
- ansible
- set inventory file ansible-files/inventory.ini
- create ssh key:
    `ssh-keygen -t rsa -b 4096 -f ansible-files/ansible.key`

## Deploy
- Provisioning servers: `ansible-playbook -e user=carlos playbook-provisioning.yml`
- Deploy cluster swarm: `ansible-playbook -e user=carlos playbook-masters.yml`
- Join works to master: `ansible-playbook -e user=carlos playbook-workers.yml`
- Deploy elk stack: `ansible-playbook -e user=carlos playbook-stack.yml`