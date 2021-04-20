Blueprint
=========

Deploy stack through Ambari's blueprint API

Requirements
------------

YUM Repository with HDP packages and dependencies reachable
Tested on CentOS 7 & Ambari 2.7.4.0 + HDP 3.1.4.0

Role Variables
--------------

```yaml
ambari_server: localhost
ambari_port: 8080

blueprint_name: molecule
cluster_name: molecule

hdp_version: 3.1.4.0

cluster_template: "{{ lookup('file', 'cluster_template.json') }}"
cluster_blueprint: "{{ lookup('file', 'cluster_blueprint.json') }}"

ambari_admin_user: admin
ambari_admin_password: newpassword

wait: yes
wait_timeout: 5
```

Example Playbook
----------------

```yaml
- hosts: localhost
  connection: local
  roles:
  - role: klusters.ambari.blueprint
```
To Do
----------------

 - [x] Basic Blueprint
 - [ ] Configure Services
 - [ ] Add Security support

License
-------

MIT
