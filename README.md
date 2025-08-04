# Ansible Utilities Playbooks Project

## Overview

Welcome aboard fellow developer, this git project was borned after I have to change the notebook to a new one with diferent OS, so a create this repository to execute the ansible and install all the applications I need to work and do my personal stuffs at once to save time and cognitive overhelming (something a lot of things is going on and I need to preserve my low energy). This project became I source of knowledge to do many thing I've learned and/or inspire new ideas into software/infrastructure project likewise my software/infrastructure personal endeavors.

## How to use this project

This repository is organized into `roles` folder to each application installation. An application can have dependencies and I try to reuse roles to ensure everything application needs is installed. Most of application have `Linux` and `MacOS` installation, sometimes they are common for both OSs, sometimes not, but I use tags to group those installation by application and the installation is conditional according to OS the application and calls a specif role. The play book running is for `local` installation, so you have to clone this project in the machine we're gonna run the playbook. If you want to run remote installation, you can change it in the `hosts` file.

## Requirements

You're gonna need this tools to use this project:

* [PyEnv 2.3.x](https://github.com/pyenv/pyenv) or greater (Optional)
* [Python 3.8.x](https://www.python.org/downloads/release/python-380/)
* [Ansible 2.10](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) or greater

## Commands

To run all the playbook roles, you can perform:

```sh
$ ansible-playbook main.yml -i hosts
PLAY [localhost] ******************************************************************************************************************************************

TASK [Gathering Facts] ************************************************************************************************************************************
ok: [localhost]

TASK [microk8s_macos : MicroK8S MacOS installation] *******************************************************************************************************
skipping: [localhost]

TASK [microk8s_macos : Gettting version installed] ********************************************************************************************************
skipping: [localhost]

TASK [microk8s_macos : debug] *****************************************************************************************************************************
ok: [localhost] => {
    "msg": "..."
}

PLAY RECAP ************************************************************************************************************************************************
localhost                  : ok=2    changed=0    unreachable=0    failed=0    skipped=4    rescued=0    ignored=0
```

To run a specific playbook role, you can perform with it declared in the command line:

```sh
$ ansible-playbook main.yml -i hosts --tags gnupg_role -K
.
```

To list all the roles, you can perform:

```sh
$ ansible-playbook main.yml -i hosts --list-tags
.
```

## Applications Available

| Application                    | Version  | SOs   |
|--------------------------------|----------|-------|
| AWS Cli                        | 2.x      | MacOS |
| AWS VPN Cl                     | Latest   | MacOS |
| Azure Cli                      | Latest   | MacOs |
| CodeLite                       | Latest   | MacOS |
| GVM - Golang Version Manager   | Latest   | MacOs |
| MicroK8S                       | Latest   | MacOs |
| Multipass                      | Latest   | MacOs |
| NGrok                          | Latest   | MacOS |
| Notion                         | Latest   | MacOS |
| RVM - Ruby Version Manager     | Latest   | MacOs |
| Slack                          | 4.45.6   | MacOs |
| Terraform                      | 0.12.31  | MacOS |
| TFEnv                          | Latest   | MacOS |
| TFSec                          | Latest   | MacOS |
| Vagrant                        | Latest   | MacOS |
