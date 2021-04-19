Server
=========

Install & Configure Ambari server

Requirements
------------

YUM Repository with ambari-server package and dependencies reachable
Tested on CentOS 7 & Ambari 2.7.4.0

Role Variables
--------------

```yaml
ambari_server: localhost

java_path: '/usr/lib/jvm/java'

ambari_https: no
ambari_port: 8080

config_logs: no
base_logs_path: /var/log

postgres_port: 5432
postgres_jdbc_location: /usr/share/java/postgresql-jdbc.jar
postgres_packages:
  - postgresql
  - python-psycopg2
  - postgresql-jdbc

database: mariadb
mysql_port: 3306
mariadb_jdbc_location: /usr/share/java/mysql-connector-java.jar
mariadb_packages:
  - mysql
  - MySQL-python
  - mysql-connector-java

database_options:
  external_hostname: "{{ groups['db'] | first }}"
  ambari_db_name: molecule
  ambari_db_username: molecule
  ambari_db_password: molecule

ambari_properties:
- "server.startup.web.timeout=120"
- "server.jdbc.driver.path={{ lookup('vars', database + '_jdbc_location') }}"
- "client.api.port={{ ambari_port }}"
```

Example Playbook
----------------

```yaml
- hosts: localhost
  connection: local
  roles:
  - role: klusters.ambari.server
```
To Do
----------------

 - [x] Configure Logs
 - [x] Configure with MariaDB
 - [x] Configure with Postgres
 - [x] Test with MariaDB
 - [ ] Test with Postgres
 - [ ] Configure Ambari Server with LDAP auth
 - [ ] Configure Ambari Server with HTTPS


License
-------

MIT