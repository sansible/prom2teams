# prom2teams 

Master: [![Build Status](https://travis-ci.org/sansible/prom2teams.svg?branch=master)](https://travis-ci.org/sansible/prom2teams)  
Develop: [![Build Status](https://travis-ci.org/sansible/prom2teams.svg?branch=develop)](https://travis-ci.org/sansible/prom2teams)

* [ansible.cfg](#ansible-cfg)
* [Installation and Dependencies](#installation-and-dependencies)
* [Tags](#tags)
* [Examples](#examples)

This roles installs prom2teams.

prom2teams allows alerts to be sent from Prometheus Alert Manager to Microsoft Teams.

For more information about prom2teams please visit
[https://github.com/idealista/prom2teams](https://github.com/idealista/prom2teams).

For more information about Prometheus Server please visit
[https://prometheus.io](https://prometheus.io).

For more information about Prometheus Alert Manager please visit
[https://prometheus.io/docs/alerting/](https://prometheus.io/docs/alerting/)


This role installs Python 3.5 and Pip 9.0.1 in a virtual environment as this a requirment of prom2teams and Python 3.5 is not currently available in Ubuntu 14.04.

## ansible.cfg

This role is designed to work with merge "hash_behaviour". Make sure your
ansible.cfg contains these settings

```INI
[defaults]
hash_behaviour = merge
```




## Installation and Dependencies

This role will install `sansible.users_and_groups` for managing `prom2teams` user.

To install run `ansible-galaxy install sansible.prom2teams` or add this to your
`roles.yml`.

```YAML
- name: sansible.prom2teams
  version: v1.0
```

and run `ansible-galaxy install -p ./roles -r roles.yml`




## Tags

This role uses tags: **build** and **configure**

* `build` - Installs prom2teams and all it's dependencies.
* `configure` - configure prom2teams



## Examples

Simply include role in your playbook

Default port: 8089

```YAML
- name: Install and configure prom2teams
  hosts: "somehost"

  roles:
    - role: sansible.prom2teams
```

```YAML
- name: Install and configure prom2teams.
  hosts: "somehost"

  roles:
    - role: sansible.prom2teams
      sansible_prom2teams:
        port: 1234
        webhook_url: http://myteamsurl/ 
```
