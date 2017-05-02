# Zookeeper

## Tags

This role uses two tags: **build** and **configure**

* `build` - Installs Zookeeper server and all it's dependencies.
* `configure` - Configure and ensures that the Zookeeper service is running.

## AWS Cluster Autodiscovery

The [AWS Autodiscover script](/files/aws_cluster_autodiscover) allows machines to pick an
ID and a hostname from a predefined list, AWS tags are used to mark machines that have
claimed an ID/host.

This script allows for a static set of hostnames with consistent IDs, the details of the machines that
claim these details can change, so no need for hardcoded IPs or network drives. As long as a machine is
recognised by the rest of the cluster then it will automatically join and sync with the other machines.

## Examples

```YAML
- name: Install Zookeeper Server
  hosts: sandbox

  pre_tasks:
    - name: Update apt
      become: yes
      apt:
        cache_valid_time: 1800
        update_cache: yes
      tags:
        - build

  roles:
    - name: zookeeper
```
