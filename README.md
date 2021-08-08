# Ansible Configurations and Playbooks

## Table of Contents
* [General Info](#general-info)
* [Technologies](#technologies)
* [Playbooks](#playbooks)

## General Info
This public repository consists of the configurations and playbooks used in 12128489 Canada Inc's automation infrastructure, excluding any confidential information.

## Technologies
This project is created with:
* Debian version: 10 amd64
* Ansible version: 2.7.7

## Playbooks
Commands starting with `$` denote a non-root user, while commands starting with `#` denote the root user.

### Debian 10
#### Debian 10 Default Configuration
To run the debian-defaults ansible playbook for the first time on a fresh install with only the `root` user configured, ensure you're in the Ansible directory (`/home/sysadmin/ansible`) and run the following command on the ansible server:
```
$ ansible-playbook -i hosts -l {TARGET_HOSTNAME_HERE} playbooks/debian-buster-defaults/playbook.yml -u root -k
```

If you already have a fresh install with a new user configured, ensure you're in the Ansible directory (`/home/sysadmin/ansible`) and run the following command on the ansible server:
```
$ ansible-playbook -i hosts -l {TARGET_HOSTNAME_HERE} playbooks/debian-buster-defaults/playbook.yml -u sysadmin -K
```

#### Debian 10 Docker Configuration
NOTE: Ensure that the Debian 10 Default Configuration playbook has been successfully run prior to executing this playbook.

Ensure you're in the Ansible directory (`/home/sysadmin/ansible`) and run the following command on the ansible server:
```
$ ansible-playbook -i hosts -l {TARGET_HOSTNAME_HERE} playbooks/debian-buster-docker/playbook.yml
```

#### Debian 10 Core Routing Configuration
NOTE: Ensure that the Debian 10 Default Configuration playbook has been successfully run prior to executing this playbook.

Ensure you're in the Ansible directory (`/home/sysadmin/ansible`) and run the following command on the ansible server:
```
$ ansible-playbook -i hosts -l {TARGET_HOSTNAME_HERE} playbooks/debian-buster-core-routing/playbook.yml
```

#### Debian 10 Update
Ensure you're in the Ansible directory (`/home/sysadmin/ansible`) and run the following command on the ansible server:
```
$ ansible-playbook -i hosts -l {TARGET_HOSTNAME_HERE} playbooks/debian-buster-updates.yml
```

### CentOS 7
#### CentOS 7 Default Configuration
To run the centos-7-defaults ansible playbook for the first time on a fresh install with only the `root` user configured, ensure you're in the Ansible directory (`/home/sysadmin/ansible`) and run the following command on the ansible server:
```
$ ansible-playbook -i hosts -l {TARGET_HOSTNAME_HERE} playbooks/centos-7-defaults/playbook.yml -u root -k
```

If you already have a fresh install with a new user configured, ensure you're in the Ansible directory (`/home/sysadmin/ansible`) and run the following command on the ansible server:
```
$ ansible-playbook -i hosts -l {TARGET_HOSTNAME_HERE} playbooks/centos-7-defaults/playbook.yml -u sysadmin -k -K
```

#### CentOS 7 Update
Ensure you're in the Ansible directory (`/home/sysadmin/ansible`) and run the following command on the ansible server:
```
$ ansible-playbook -i hosts -l {TARGET_HOSTNAME_HERE} playbooks/centos-7-updates/playbook.yml
```

