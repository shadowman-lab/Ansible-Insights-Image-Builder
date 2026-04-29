<!-- This was created with Claude Code -->

# Insights Image Builder Automation

[![Contribute](https://img.shields.io/badge/OpenShift-Dev%20Spaces-525C86?logo=redhatopenshift&labelColor=EE0000)](https://devspaces.apps.ocp.shadowman.dev/#https://github.com/shadowman-lab/Ansible-Insights-Image-Builder)


This directory contains Ansible automation for insights image builder management and operations.

## Overview

The Insights Image Builder automation provides playbooks and roles for managing and configuring
insights image builder infrastructure and services.

## Roles

| Role | Description |
| ---- | ----------- |
| [image_builder](roles/image_builder/README.md) | Role for image builder |

## Playbooks

| Playbook | Description | Target Hosts |
| -------- | ----------- | ------------ |
| cleanup-composes.yml | Playbook for cleanup-composes | localhost |
| delete-compose.yml | Playbook for delete-compose | localhost |
| lifecycle-images.yml | Playbook for lifecycle-images | localhost |
| list-composes.yml | Playbook for list-composes | localhost |
| list-distributions.yml | Playbook for list-distributions | localhost |
| request_and_download_images.yml | Playbook for request and download images | localhost |

## Usage

### Running with ansible-navigator

```bash
# Run a playbook
ansible-navigator run cleanup-composes.yml

# Run in stdout mode
ansible-navigator run cleanup-composes.yml -m stdout
```

### Using roles

```yaml
- hosts: target_hosts
  roles:
    - image_builder
```

## Requirements

- Ansible 2.9 or higher (via ansible-navigator)
- Required collections (see `collections/requirements.yml` if present)
- Appropriate access credentials configured via environment variables

## Directory Structure

```
Ansible-Insights-Image-Builder/
├── roles/              # Ansible roles
├── *.yml               # Playbooks
├── collections/        # Collection dependencies (if present)
└── ansible-navigator.yml  # Navigator configuration
```
