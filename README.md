# Ansible

ansible-playbook playbook/$playbook --limit $hosts --check --diff

#### Xtls 
Debian-based systems compatible.

- init tag will create vm users, configure sshd and simple firewall:
```
ansible-playbook playbook/xtls-server.yaml --tag init --limit $hosts
```
- install-packages tag will only add packages and restart services:
```
ansible-playbook playbook/xtls-server.yaml --tag install-packages --limit $hosts
```
- use playbook to configure all system.
add ur ssl-certificates manually 
before run this command:
```
ansible-playbook playbook/xtls-server.yaml --skip-tag backup --limit $hosts
```
- to backup (.db format) data use:
```
ansible-playbook playbook/xtls-server.yaml --tag backup --limit $hosts
```

**Future features:**  
- automated ssl-cert claim & renewal
- uninstall mode for roles
- direct xtls config editing
- redhat-based systems compatibility
- blacklist firewall
- ansible-vault