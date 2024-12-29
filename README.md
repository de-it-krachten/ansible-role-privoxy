[![CI](https://github.com/de-it-krachten/ansible-role-privoxy/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-privoxy/actions?query=workflow%3ACI)


# ansible-role-privoxy

Manage privoxy 



## Dependencies

#### Roles
None

#### Collections
None

## Platforms

Supported platforms

- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS
- Fedora 40
- Fedora 41

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# List of packages
privoxy_packages:
  - privoxy

# Privoxy service name
privoxy_service: privoxy

# privoxy ip
privoxy_ip: "{{ ansible_default_ipv4.address }}"

# privoxy port
privoxy_port: 8118

privoxy_settings:
  "listen-address": "{{ privoxy_ip }}:{{ privoxy_port }}"
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'privoxy'
  hosts: all
  become: 'yes'
  tasks:
    - name: Include role 'privoxy'
      ansible.builtin.include_role:
        name: privoxy
</pre></code>
