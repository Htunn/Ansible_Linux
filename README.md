# Prerequisites

# For Debian 

sudo apt install software-properties-common

sudo apt-add-repository --yes --update ppa:ansible/ansible

sudo apt install python-software-properties

sudo apt install python3-pip

sudo apt install ansible

ansible --version 


# To use Python3 in Ansible

sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.5 2
update-alternatives --config python3


# To install Ansible with pip  

pip3 install ansible

# to manage docker with ansible

pip3 install docker-py


# To test ansible for local host ( with local connection)

ansible localhost -m ping -c local"

ansible-playbook main.yml -c local -i "localhost,"


# To implement Ansible Environment in Linux

# On Control Node

- create user and ssh-key pairs for ansible

$ useradd -m -s /bin/bash ansible
$ passwd ansible
$ ssh-keygen
$ ssh-copyid ansible@(managed node addr)

# create sudoers file for ansible to achieve passwordless auth

sudo vim /etc/sudoers.d/ansible

ansible ALL=(ALL) NOPASSWD: ALL

- %ansible for group
-  ansible for user

# On Managed Nodes

- create ansible user 
- create sudoers file ( same as above steps )
- allow ssh port 22 or whatever port range for ssh connection


# Testing Ansible Env with Ansible ad hoc command

  # On Control Node 

  - create inventory file
  - define fqdn or ip address of managed node with ini or yaml
  - modify ansible.cfg for your env


# Test Ansible ad hoc command

$ ansible -i inventory -m ping 

$ ansible -i inventory -m ping -b # test privilege escalation

