Here, we use Ansible to configure the following on our host machines:
- Install apache2 and host 2048 game on it
- Install and setup node exporter for Prometheus
- Install and setup apache exporter for Prometheus

We do this by:
1. using playbooks
2. using roles

cd into the directory of your choice to get started.

This assumes you have a machine (VM) with a public IP address and you can ssh into it as the root user.

**Ensure**:
- the ansible user is created on the remote machine and has sudo privileges.
- your public ssh key is added to the ansible user's authorized_keys file.
