# ansible-traceroute

This program pings a set of destinations laid out in the hosts file and returns the results

## Requirements

The host this ansible play runs on must meet the following requirements:

* Must be a linux host
* Must have the following installed
 * python3
 * ansible
 * ping
 * traceroute

## Usage

```
ansible-playbook playbook.yml
```

## Ansible Modifications

The following modifications were made to ansible.cfg:

* inventory was pointed towards the hosts file in the programs directory
* For my own notes, the following are methods that can be used to force the play to run the commands via the local machine:

 * using Ansible command line:

```bash
ansible-playbook --connection=local 127.0.0.1 playbook.yml
```

 * using inventory:

```ini
127.0.0.1 ansible_connection=local
```

 * using Ansible configuration file:

```ini
[defaults]
transport = local
```

 * using playbook header:

```yaml
- hosts: 127.0.0.1
  connection: local
```
