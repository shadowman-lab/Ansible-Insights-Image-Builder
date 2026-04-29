<!-- This was created with Claude Code -->

image_builder
=============

An Ansible role for image builder.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **sso_endpoint**: Endpoint required to request offline token
  - Default: `https://sso.redhat.com/auth/realms/redhat-external/protocol/openid-connect/token`

* **api_endpoint**: Endpoint required to interact with image builer
  - Default: `https://console.redhat.com/api/image-builder/v1`

* **storage_dir**: Where to copy the images when downloading and customizing
  - Default: `/tmp`

* **compose_check_retries**: How many times to check the status of image builds
  - Default: `15`

* **compose_check_wait_secs**: For how long to wait between each image build status check
  - Default: `60`

* **compose_check_max_loops**: How many loops of `compose_check_retries` to do, while renewing token in between loops (if expired)
  - Default: `5`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: image_builder
      vars:
        sso_endpoint: <value>
        api_endpoint: <value>
        storage_dir: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
