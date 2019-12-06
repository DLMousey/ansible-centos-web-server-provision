# Ansible CentOS7 web server provisioning

This playbook will do the following on a brand spankin' new CentOS7 node;

- Disable SELinux
- Install NGINX
- Install Docker
- Install NodeJS (+ NPM)

## Setup

On your "Control Node" (the machine you want to run ansible commands from, not the node you intend to configure),
generate a new SSH key;

- Install Ansible following the instructions [in the documentation](https://docs.ansible.com/ansible/latest/installation_guide/index.html)
- Generate a new SSH Keypair: ```ssh-keygen -t rsa```
- Name this keyfile something you'll recognise, place it somewhere safe (very safe)
- Copy the key to your new CentOS7 node - ```ssh-copy-id -i ~/.ssh/your_key_file root@your_centos7_node```
- Don't freak out! Root access is the simplest way of setting up the utilities we need
- Adjust the `inventory` file, ensure it has the hostnames and ip addresses of any node(s) you want to set up
- Run `ansible-playbook web-server-provision.yml`
- Cross fingers
