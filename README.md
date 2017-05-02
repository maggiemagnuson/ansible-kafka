# ansible-kafka :: Version 0.01

Ansible Playbook to set up Zookeeper and Kafka

# Zookeeper

This roles installs Apache Zookeeper server.

For more information about Zookeeper please visit
[zookeeper.apache.org/](http://zookeeper.apache.org/).

# Kafka

And this roles installs Apache Kafka server.

For more information about Kafka please visit
[zookeeper.apache.org/](http://kafka.apache.org/).

## Tags

This role uses two tags: **build** and **configure**

* `build` - Installs Kafka server and all it's dependencies.
* `configure` - Configure and ensures that the Kafka service is running.

## Examples

If you want to run both Zookeeper and Kafka on the same machine.

```YAML
- name: Install Kafka Server
  hosts: all

  roles:
    - name: zookeeper
    - name: kafka
```
