Agent
=========

Install & Configure Ambari Agent

Requirements
------------

YUM Repository with ambari-agent package and dependencies reachable
Tested on CentOS 7 & Ambari 2.7.4.0

Role Variables
--------------

| Variable                 | Required | Default                                                                  | Comments                                        |
| ------------------------ | -------- | ------------------------------------------------------------------------ | ----------------------------------------------- |
| `ambari_server`                | No | `localhost` | Ambari Server FQDN |
| `config_logs`                | No | `no`          | Configure or not logs path |
| `base_logs_path`                | No | `/var/log` | Path to store ambari agent logs |

Example Playbook
----------------

```yaml
- hosts: localhost
  connection: local
  roles:
  - role: klusters.ambari.agent
```

License
-------

MIT
