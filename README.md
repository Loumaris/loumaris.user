# loumaris.user

A small playbook to setup a user on a linux system like ubuntu.

## usage

Example inside another role:

```yaml
---
- name: create user
  become: true
  include_role:
    name: common.user
  vars:
    username: 'cheimke'
    fullname: 'Christian Heimke'
    sudo: true
    password: "{{ user__cheimke_password }}"
```

Example inside a playbook:

```yaml
- name: apply common configuration to all nodes
  hosts: all
  roles:
    - { role: loumaris.user, username: 'cheimke', fullname: 'Christian Heimke', sudo: true, password: "{{ user__cheimke_password }}" }
```
## configuration

Possible parameter with default:

* `sudo`: true
* `shell`: "/bin/bash"
* `state`: present
* `group`: users