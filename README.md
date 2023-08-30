Create a file called inventory and add the following content:
```ini
[vm]
vm1 ansible_host=<public IP> ansible_ssh_user=ansible ansible_ssh_private_key_file=~/.ssh/ansible
```

To run your playbook:
```bash
ansible-playbook -i inventory main.yaml -K
# then enter your sudo password for the ansible user
```