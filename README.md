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

```
ansible-playbook main.yml -i hosts
```

To run a specific playbook role, you can perform with it declared in the command line:

```
ansible-playbook main.yml -i hosts --tags gnupg_role -K
```

To list all the roles, you can perform:

```
ansible-playbook main.yml -i hosts --list-tags

```

## Applications Available

| Application                    | Version  | SOs   |
|--------------------------------|----------|-------|
| AWS Cli                        | 2.x      | MacOS |
| Azure Cli                      | Latest   | MacOs |
| GVM - Golang Version Manager   | Latest   | MacOs |
| RVM - Ruby Version Manager     | Latest   | MacOs |
