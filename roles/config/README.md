Config
=========

Install & Configure Ambari server

Requirements
------------

YUM Repository with ambari-server package and dependencies reachable
Tested on CentOS 7 & Ambari 2.7.4.0

Role Variables
--------------

```yaml
ambari_server: "{{ groups['ambari_server'] | first }}"

hdp_version: 3.1.4.0
hdp_build_number: 315
utils_version: 1.1.0.22

hdp_minor_version: "{{ hdp_version | regex_replace('.[0-9]+.[0-9]+[0-9_-]*$','') }}"
hdp_major_version: "{{ hdp_minor_version.split('.').0 }}"

ambari_port: 8080

hdp_install: true
hdf_install: false
install_hdpsearch: false

yum_baseurl: "{{ lookup('env', 'HDP_YUM_BASEURL') }}"
yum_username: "{{ lookup('env', 'AMBARI_YUM_USERNAME') }}"
yum_password: "{{ lookup('env', 'AMBARI_YUM_PASSWORD') }}"

ambari_admin_user: 'admin'
ambari_admin_password: 'newpassword'
ambari_admin_default_password: 'admin'

os_family: "redhat7"
hdp_main_repo_url: "{{ yum_baseurl }}/HDP/{{ hdp_version }}"
utils_repo_url: "{{ yum_baseurl }}/HDP-UTILS/{{ utils_version }}"
```

Example Playbook
----------------

```yaml
- hosts: localhost
  connection: local
  roles:
  - role: klusters.ambari.config
```


License
-------

MIT
