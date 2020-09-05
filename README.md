# Ansible role for Docker
1. Install role
```
ansible-galaxy install -r requirements.yml
```
2. Run playbook
```
ansible-playbook -i localhost, playbook.yml -e 'ansible_user=packer ansible_ssh_pass="packer" ansible_sudo_pass="packer"'