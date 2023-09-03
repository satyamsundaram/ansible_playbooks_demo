Here, we make use of roles from ansible-galaxy to make our playbook more modular and reusable.

This assumes you have a machine (VM) with a public IP address and you can ssh into it as the root user.

**Create a file called "inventory" and add the following content**:
```ini
[vm]
vm1 ansible_host=<public IP> ansible_ssh_user=ansible ansible_ssh_private_key_file=~/.ssh/ansible
# add more machines here if you have them
```

Create the same inside each role's tests directory as well.

**Ensure**:
- the ansible user is created on the remote machine and has sudo privileges.
- your public ssh key is added to the ansible user's authorized_keys file.


**To create a new role**:
```bash
cd roles
ansible-galaxy init <role_name>
```

Here's what the different directories mean:
- **defaults**: default variables for the role
- **files**: files that can be used by the role
- **handlers**: handlers for the role
- **meta**: metadata for the role
- **tasks**: tasks for the role
- **templates**: templates that can be used by the role
- **vars**: variables for the role
- **README.md**: documentation for the role

**To run your playbook**:
```bash
ansible-playbook -i inventory <playbook_name> -K
# then enter your sudo password for the ansible user
```
