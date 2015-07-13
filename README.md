## ssh-client

[![Build Status](https://travis-ci.org/Oefenweb/ansible-ssh-client.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-ssh-client) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-ssh--client-blue.svg)](https://galaxy.ansible.com/list#/roles/4192)

Set up an OpenSSH client in Debian-like systems.

#### Requirements

None

#### Variables

* `ssh_client_install`: [default: `[]`]: Additional packages to install

## Dependencies

None

#### Example

```yaml
---
- hosts: all
  roles:
    - ssh-client
```

#### License

MIT

#### Author Information

Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-ssh-client/issues)!
