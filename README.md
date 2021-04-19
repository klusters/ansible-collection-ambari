# Ansible Collection - klusters.ambari
[Inspired by ericsysmin.system](https://galaxy.ansible.com/ericsysmin/system)

Ansible collection that holds roles, that can be used with Ambari Managed Clusters.

## Roles

| Role      | Build Status                                                                                                                                                                                                                                                        | Documentation                                                                                          |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
|  agent   | ![klusters.ambari.agent](https://github.com/klusters/ansible-collection-ambari/workflows/klusters.ambari.agent/badge.svg)          | [Documentation](https://github.com/klusters/ansible-collection-ambari/tree/main/roles/agent)    |
|  server   | ![klusters.ambari.server](https://github.com/klusters/ansible-collection-ambari/workflows/klusters.ambari.server/badge.svg)          | [Documentation](https://github.com/klusters/ansible-collection-ambari/tree/main/roles/server)    |
|  repo   | ![klusters.ambari.repo](https://github.com/klusters/ansible-collection-ambari/workflows/klusters.ambari.repo/badge.svg)          | [Documentation](https://github.com/klusters/ansible-collection-ambari/tree/main/roles/repo)    |
|  config   | ![klusters.ambari.config](https://github.com/klusters/ansible-collection-ambari/workflows/klusters.ambari.config/badge.svg)          | [Documentation](https://github.com/klusters/ansible-collection-ambari/tree/main/roles/config)    |

## Usage

You can find specific to each role within the "Documentation" link for each role. However, most should be in this format:

Install this ansible collection :
```bash
ansible-galaxy collection install klusters.ambari
```

Write a playbook file *playbook_name.yml* :

```yaml
---
- hosts: localhost

  tasks:
    - include_role:
        name: klusters.ambari.<role_name>
```

Run *playbook_name.yml* :
```bash
ansible-playbook playbook_name.yml
```

## Testing

Testing is done through GitHub Actions, and can be tested locally as well.

To be able to test locally:
- install docker & molecule
- run molecule test

For example, on MacOS:
```bash
pip install molecule[docker]
```

Each workflow pertains to a single role, and can be launched locally using the following command:

```bash
molecule test -s <role_name>
```
