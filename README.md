# ansible-lab


This is a lightweight, practical automation lab built with **Ansible**, **Jenkins**, and **Rocky Linux** for hands-on infrastructure testing and pipeline automation.

## Repository Structure

```
ansible-lab/
├── inventory/                  # Ansible inventory file (targets: Rocky)
│   └── inventory.ini
├── playbooks/                 # Playbooks for automation
│   └── setup_nginx.yml        # Installs and starts Nginx on Rocky
├── jenkins/                   # Jenkins pipeline definition
│   └── Jenkinsfile
└── README.md                  # This file
```

## What This Lab Does

- Uses Ansible to manage a remote Rocky Linux VM
- Installs and ensures Nginx is running
- Runs from Jenkins via a simple pipeline

## Jenkins Pipeline

This repo includes a `Jenkinsfile` to automate execution of the Ansible playbook.  
Set up a Jenkins job with:
- SCM: Git
- Script Path: `jenkins/Jenkinsfile`

### Jenkins Prerequisites

- Jenkins server with:
  - Ansible installed
  - An SSH key added to Jenkins credentials
- Target Rocky host must allow SSH from Jenkins runner

## Security Notice

The `inventory.ini` contains plaintext credentials — this is intentional for lab use only.  
**Never do this in production.**

