DEPRECATED - Ansible Role Sync to S3
====================================

Use https://github.com/Aplyca/ansible-role-syncs3content instead


An Ansible role that sync app content to S3

Ansible Role that sync content to S3 on Debian/Ubuntu.

Requirements
------------

Use hash behavior for variables in ansible.cfg
See example: https://github.com/Aplyca/ansible-role-synctos3/blob/master/tests/ansible.cfg
See official docs: http://docs.ansible.com/intro_configuration.html#hash-behaviour

Installation
------------

Using ansible galaxy:

```bash
ansible-galaxy install aplyca.Synctos3
```
You can add this role as a dependency for other roles, add the role to the meta/main.yml file of your own role:

```yaml
dependencies:
  - { role: aplyca.Synctos3 }
```

Ask for confirmation
--------------------
This is a risky tasks so the role ask for a variable `confirmation`, you can add the confirmation in the playbook, like this: 

```yaml
---
- hosts: sync.server.com
  gather_facts: no
  vars_prompt:
    - name: "confirmation"
      prompt: "Are you sure to sync content to S3 [y/n]?"
  roles:
    - { role: aplyca.Synctos3, tags: ["tos3"] }
```

Role Variables
--------------
See default variables: https://github.com/Aplyca/ansible-role-synctos3/blob/master/defaults/main.yml

Dependencies
------------

- MySQL
- AWS CLI


License
-------

MIT / BSD

Author Information
------------------

Mauricio Sánchez from Aplyca SAS (http://www.aplyca.com)
