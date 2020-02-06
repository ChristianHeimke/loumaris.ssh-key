# loumaris.ssh-key

A small playbook to setup an ssh key for a specific user.

## usage

Example inside another role:

```yaml
---
- name: add ssh key
  become: true
  include_role:
    name: loumaris.ssh-key
  vars:
    username: 'cheimke'
    keyfile: 'cheimke'
    state: present

```

Example inside a playbook:

```yaml
- name: apply common configuration to all nodes
  hosts: all
  roles:
    - { role: loumaris.ssh-key, username: 'cheimke', keyfile: 'cheimke' }
```
## configuration

You need to set the following parameter:

* `username`
* `keyfile`

You need also to place the public file (e.g. `cheimke.pub`) inside the `files/ssh/public_keys` folder.