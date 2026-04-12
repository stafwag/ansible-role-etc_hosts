# Ansible Role: etc_hosts

An ansible role to manage /etc/hosts

## Installation

### Ansible galaxy

The role is available on [Ansible Galaxy](https://galaxy.ansible.com/stafwag/etc_hosts).

To install the role from Ansible Galaxy execute the command below.

```bash
ansible-galaxy install stafwag.etc_hosts
```

### Source Code

If you want to use the source code directly.

Clone the role source code.

```bash
$ git clone https://github.com/stafwag/ansible-role-etc_hosts/ stafwag.etc_hosts
```

and put into the [role search path](https://docs.ansible.com/ansible/2.4/playbooks_reuse_roles.html#role-search-path)


## Requirements

None

## Role Variables

### OS related variables

none

### Playbook related variables

* **etc_hosts**:
  * **hosts**: Array of hosts
    * **name**: hostname.
    * **ip**: ip address
    * **state**: "absent"|"present" (default)

## Dependencies

None

## Example Playbooks

```
- name: Configure /etc/hosts on dmz systems
  hosts: all
  become: true
  vars:
    etc_hosts:
      hosts:
        - { name: "localhost", ip: "127.0.0.1", state: "present" }
        - { name: "stafgit", ip: "10.10.10.10", state: "present" }
        - { name: "stafmail", ip: "10.10.10.10", state: "absent" }
  roles:
    - stafwag.etc_hosts
```

## License

MIT/BSD

## Author Information

Created by Staf Wagemakers, Email: staf@wagemakers.be, Website: [https://www.wagemakers.be](https://www.wagemakers.be), My company: [https://mask27.dev](https://mask27.dev)

***Have fun!***
