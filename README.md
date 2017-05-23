# Ansible scripts

A simple repository of my Ansible playbook

Reference : http://docs.ansible.com/

## Installation

http://docs.ansible.com/ansible/intro_installation.html

You should install ansible by python package manager pip

```bash
sudo pip install ansible
```

### Special mention on paramiko

http://www.paramiko.org/

You should keep a look on this ssh2 implementation tool used by Ansible itself.

```bash
sudo pip install paramiko
```

### First steps

#### Install openssh

Depending on your system, the way to install openssh can change.
On my MAC it is simple as : 

```bash
brew update
brew install openssh
```

#### Create /etc/ansible/hosts for ansible inventory

Simply create and file /etc/ansible/hosts (and give you suffisant write rights on it)

```bash
sudo mkdir /etc/ansible
sudo touch /etc/ansible/hosts
sudo chmod a+rx /etc/ansible
sudo chmod a+rw /etc/ansible/hosts
```

And add your localhost (mainly for testing purpose for now)

```bash
sudo echo "
[targets]
localhost              ansible_connection=local
" >> /etc/ansible/hosts
```

You can now issue a very first ansible command to localhost : 

```bash
ansible localhost -m ping -e 'ansible_python_interpreter="/usr/bin/env python"'
localhost | SUCCESS => {
    "changed": false, 
    "ping": "pong"
}
```


