## ssh-client

[![Build Status](https://travis-ci.org/Oefenweb/ansible-ssh-client.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-ssh-client) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-ssh--client-blue.svg)](https://galaxy.ansible.com/Oefenweb/ssh-client)

Set up an OpenSSH client in Debian-like systems.

#### Requirements

None

#### Variables

* `ssh_client_install`: [default: `[]`]: Additional packages to install

* `ssh_client_configurations`: [default: `ssh_client_default_configuration`, see `vars/main.yml`]: Configuration declaration(s)
* `ssh_client_configurations.{n}.dest`: [required]: The remote path of the configuration file (e.g. `/etc/ssh/ssh_config`, `~cacti/.ssh/config`)
* `ssh_client_configurations.{n}.owner`: [default: `root`]: The name of the user that should own the file
* `ssh_client_configurations.{n}.group`: [default: `owner`, `root`]: The name of the group that should own the file
* `ssh_client_configurations.{n}.hosts`: [default: `[]`]: Host declaration(s)
* `ssh_client_configurations.{n}.hosts.{n}.pattern`: [required]: Pattern to match hosts (e.g. `*`, `['*.co.uk', '192.168.0.?']`)
* `ssh_client_configurations.{n}.hosts.{n}.host_name`: [optional]: Specifies the real host name to log into. This can be used to specify nicknames or abbreviations for hosts
* `ssh_client_configurations.{n}.hosts.{n}.forward_agent`: [optional]: Specifies whether the connection to the authentication agent (if any) will be forwarded to the remote machine
* `ssh_client_configurations.{n}.hosts.{n}.forward_x11`: [optional]: Specifies whether X11 connections will be automatically redirected over the secure channel and DISPLAY set
* `ssh_client_configurations.{n}.hosts.{n}.forward_x11_trusted`: [optional]: If this option is set to `true`, remote X11 clients will have full access to the original X11 display
* `ssh_client_configurations.{n}.hosts.{n}.rhosts_rsa_authentication`: [optional]: Specifies whether to try rhosts based authentication with RSA host authentication
* `ssh_client_configurations.{n}.hosts.{n}.rsa_authentication`: [optional]: Specifies whether to try RSA authentication
* `ssh_client_configurations.{n}.hosts.{n}.password_authentication`: [optional]: Specifies whether to use password authentication
* `ssh_client_configurations.{n}.hosts.{n}.hostbased_authentication`: [optional]: Specifies whether to try rhosts based authentication with public key authentication
* `ssh_client_configurations.{n}.hosts.{n}.gssapi_authentication`: [optional]: Specifies whether user authentication based on GSSAPI is allowed
* `ssh_client_configurations.{n}.hosts.{n}.gssapi_delegate_credentials`: [optional]: Forward (delegate) credentials to the server
* `ssh_client_configurations.{n}.hosts.{n}.gssapi_key_exchange`: [optional]: Specifies whether key exchange based on GSSAPI may be used. When using GSSAPI key exchange the server need not have a host key
* `ssh_client_configurations.{n}.hosts.{n}.gssapi_trust_dns`: [optional]: Set to `true` to indicate that the DNS is trusted to securely canonicalize the name of the host being connected to. If `false`, the hostname entered on the command line will be passed untouched to the GSSAPI library
* `ssh_client_configurations.{n}.hosts.{n}.batch_mode`: [optional]: If set to `true`, passphrase/password querying will be disabled
* `ssh_client_configurations.{n}.hosts.{n}.check_host_ip`: [optional]: If this flag is set to `true`, `ssh` will additionally check the host IP address in the known_hosts file
* `ssh_client_configurations.{n}.hosts.{n}.address_family`: [optional]: Specifies which address family to use when connecting. Valid arguments are `any`, `inet` (use IPv4 only), or `inet6` (use IPv6 only)
* `ssh_client_configurations.{n}.hosts.{n}.connect_timeout`: [optional]: Specifies the timeout (in seconds) used when connecting to the SSH server, instead of using the default system TCP timeout
* `ssh_client_configurations.{n}.hosts.{n}.strict_host_key_checking`: [optional]: If this flag is set to `true`, `ssh` will never automatically add host keys to the `~/.ssh/known_hosts` file, and refuses to connect to hosts whose host key has changed
* `ssh_client_configurations.{n}.hosts.{n}.identity_file`: [optional]: Specifies a file from which the user’s RSA or DSA authentication identity is read. It is possible to have multiple identity files specified in configuration files; all these identities will be tried in sequence (e.g. `['~/.ssh/identity', '~/.ssh/id_rsa', '~/.ssh/id_dsa']`)
* `ssh_client_configurations.{n}.hosts.{n}.port`: [optional]: Specifies the port number to connect on the remote host
* `ssh_client_configurations.{n}.hosts.{n}.protocol`: [optional]: Specifies the protocol versions ssh(1) should support in order of preference (e.g. `[2, 1]`)
* `ssh_client_configurations.{n}.hosts.{n}.cipher`: [optional]: Specifies the cipher to use for encrypting the session in protocol version 1 (e.g. `3des`)
* `ssh_client_configurations.{n}.hosts.{n}.ciphers`: [optional]: Specifies the ciphers allowed for protocol version 2 in order of preference (e.g. `[aes128-ctr, aes192-ctr, aes256-ctr, arcfour256, arcfour128, aes128-cbc, 3des-cbc]`)
* `ssh_client_configurations.{n}.hosts.{n}.macs`: [optional]: Specifies the MAC (message authentication code) algorithms in order of preference (e.g. `[hmac-md5, hmac-sha1, umac-64@openssh.com, hmac-ripemd160]`)
* `ssh_client_configurations.{n}.hosts.{n}.escape_char`: [optional]: Sets the escape character (e.g. `~`)
* `ssh_client_configurations.{n}.hosts.{n}.tunnel`: [optional]: Request `tun` device forwarding between the client and the server
* `ssh_client_configurations.{n}.hosts.{n}.tunnel_device`: [optional]: Specifies the `tun` devices to open on the client (local_tun) and the server
* `ssh_client_configurations.{n}.hosts.{n}.permit_local_command`: [optional]: Allow local command execution via the `LocalCommand` option or using the `!command` escape sequence in `ssh`
* `ssh_client_configurations.{n}.hosts.{n}.visual_host_key`: [optional]: If this flag is set to `yes`, an ASCII art representation of the remote host key fingerprint is printed in addition to the hex fingerprint string at login and for unknown host keys
* `ssh_client_configurations.{n}.hosts.{n}.proxy_command`: [optional]: Specifies the command to use to connect to the server
* `ssh_client_configurations.{n}.hosts.{n}.rekey_limit`: [optional]: Specifies the maximum amount of data that may be transmitted before the session key is renegotiated
* `ssh_client_configurations.{n}.hosts.{n}.send_env`: [optional]: Specifies what variables from the local `environ` should be sent to the server
* `ssh_client_configurations.{n}.hosts.{n}.global_known_hosts_file`: [optional]: Specifies one or more files to use for the global host key database, list of files
* `ssh_client_configurations.{n}.hosts.{n}.user_known_hosts_file`: [optional]: Specifies one or more files to use for the user host key database, list of files
* `ssh_client_configurations.{n}.hosts.{n}.hash_known_hosts`: [optional]: Indicates that `ssh` should hash host names and addresses when they are added to `~/.ssh/known_hosts`
* `ssh_client_configurations.{n}.hosts.{n}.compression`: [optional]: Specifies whether to use compression
* `ssh_client_configurations.{n}.hosts.{n}.compression_level`: [optional]: Specifies the compression level to use if compression is enabled
* `ssh_client_configurations.{n}.hosts.{n}.control_master`: [optional]: Enables the sharing of multiple sessions over a single network connection (e.g. `'yes'`, `'no'`, `'ask'`, `'auto'`)
* `ssh_client_configurations.{n}.hosts.{n}.control_path`: [optional]: Specify the path to the control socket used for connection sharing as described in the `ControlMaster` section above or the string `none` to disable connection sharing (e.g. `~/.ssh/control-master/%r@%h:%p`)
* `ssh_client_configurations.{n}.hosts.{n}.control_persist`: [optional]: When used in conjunction with `ControlMaster`, specifies that the master connection should remain open in the background (waiting for future client connections) after the initial client connection has been closed (e.g. `'no'`, `'yes'`, `'60m'`)
* `ssh_client_configurations.{n}.hosts.{n}.use_roaming`: [optional]:

## Dependencies

None

#### Example

```yaml
---
- hosts: all
  roles:
    - ssh-client
  vars:
    ssh_client_custom_configurations:
      - dest: '~cacti/.ssh/config'
        owner: cacti
        hosts:
          - pattern: ['*']
            control_master: 'auto'
            control_path: '~/.ssh/control-master/%r@%h:%p'
            control_persist: '60m'
      - dest: '~vagrant/.ssh/config'
        owner: vagrant
        hosts:
          - pattern: ['bitbucket-repo-1']
            host_name: bitbucket.org
            identity_file:
              - '~/.ssh/bitbucket-repo-1'
          - pattern: ['bitbucket-repo-2']
            host_name: bitbucket.org
            identity_file:
              - '~/.ssh/bitbucket-repo-2'
    ssh_client_configurations: "{{ ssh_client_default_configuration + ssh_client_custom_configurations }}"
```

#### License

MIT

#### Author Information

Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-ssh-client/issues)!
