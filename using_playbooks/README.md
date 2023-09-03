This assumes you have a machine (VM) with a public IP address and you can ssh into it as the root user.

**Create a file called "inventory" and add the following content**:
```ini
[vm]
vm1 ansible_host=<public IP> ansible_ssh_user=ansible ansible_ssh_private_key_file=~/.ssh/ansible
```

**Ensure**:
- the ansible user is created on the remote machine and has sudo privileges.
- your public ssh key is added to the ansible user's authorized_keys file.


**To run your playbook**:
```bash
ansible-playbook -i inventory <playbook_name> -K
# then enter your sudo password for the ansible user
```