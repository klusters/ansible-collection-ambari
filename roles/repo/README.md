Repo
=========

Configure Ambari YUM REPO

Requirements
------------

YUM Repository with ambari-agent package and dependencies reachable
Tested on CentOS 7

Role Variables
--------------

```yaml
ambari_repo:
  name: Ambari-2.7.4.0
  description: 'Ambari v2.7.4.0 yum repository'
  file: ambari
  gpgcheck: no
  baseurl: "{{ lookup('env', 'AMBARI_YUM_URL') }}"
  username: "{{ lookup('env', 'AMBARI_YUM_USERNAME') }}"
  password: "{{ lookup('env', 'AMBARI_YUM_PASSWORD') }}"
```

Example Playbook
----------------

```yaml
- hosts: localhost
  connection: local
  roles:
  - role: klusters.ambari.repo
```

License
-------

MIT
