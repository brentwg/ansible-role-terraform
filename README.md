# Ansible Role - Terraform
[![Build Status](https://travis-ci.org/brentwg/ansible-role-terraform.svg?branch=master)](https://travis-ci.org/brentwg/ansible-role-terraform)

This role installs Hashicorp's [Terraform](https://www.terraform.io) application.  

This is mostly based on Jeff Geerling's [Ansible Role: Packer](https://github.com/geerlingguy/ansible-role-packer). However, I've slightly modified it to preserve previous downloaded versions and I've added a symlink so that you can switch between versions - depending on which one is specified in this role.  

## Requirements

None.

## Role Variables
User modifiable variables and defaults are listed below. (For all variables, see `defaults/main.yml`):

```
terraform_version: "0.11.3"
```  
The version of Terraform to install.  

```
terraform_arch: "amd64"
```  
The system architecture that you are using (eg. `386` or `amd64`).

The installation path is:  
```
/usr/local/terraform/{{ terraform_version }}/terraform
```  

And the symlink to the specified version is created here:  
```
/usr/local/bin/terraform
```

## Dependencies

None.

## Sample Playbook

```
- hosts: all

  vars:
    terraform_version: "0.11.3"
    terraform_arch: "amd64"

  roles:
    - brentwg.terraform
```  
