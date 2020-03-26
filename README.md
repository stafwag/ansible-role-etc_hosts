# Ansible Role: etc_hosts

An ansible role to manage /etc/hosts

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
- name: configure /etc/hosts on dmz systems
  hosts: dmz
  become: true
  vars:
    etc_hosts:
      hosts:
        - { name: "localhost", ip: "127.0.0.1", state: "present" }
        - { name: "stafgit", ip: "10.10.10.10", state: "absent" }
        - { name: "stafmail", ip: "10.10.10.10", state: "absent" }
  roles:
    - stafwag.etc_hosts
```

## License

MIT/BSD

## Author Information

Created by Staf Wagemakers, email: staf@wagemakers.be, website: http://www.wagemakers.be.
