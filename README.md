# ansible-playbooks

A collection of Ansible Playbooks for completing various tasks 

## Installation

Before running the playbooks you must ensure that ansible is installed on the server:

```
sudo apt-get install ansible
```

## Configuration

All host configuration is done within the "hosts" file in this repository. New hosts must be added to the file, including the default user to use, eg:

```
testubuntu-1604 ansible_user=root
```

New groups can be created by putting the name in square brackets, any hosts under this (before the next group) will be used when this group is targeted in the hosts section of a script

```
[testubuntu]
```

## Usage

Ansible Playbooks are stored within directories under playbooks as appropriate. New Playbooks should be stored here.

Playbooks can be called as follows:

* Update the yaml file with the host group / hostname for your target machine (May update this with a script in the future).

*NOTE: It is important to specify the hosts file in this repository using the -i flag otherwise the default will be used!*

```
ansible-playbook -i hosts playbooks/path/to/playbook.yml
```

## AWX

AWX is the opensource version of Ansible Tower. This is still a WIP but docker-compose setup is working now (Using this Github repo: https://github.com/geerlingguy/awx-container) but with official Ansible images. 

*NOTE: Will need to secure this as all settings are default currently and the Ansible playbooks dir is not mounted.*