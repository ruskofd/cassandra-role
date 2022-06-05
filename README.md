<p><img src="https://upload.wikimedia.org/wikipedia/commons/5/5e/Cassandra_logo.svg" alt="cassandra-logo" title="cassandra" align="top" height=180 /></p>

***Apache Cassandra** is an open source NoSQL distributed database trusted by thousands of companies for scalability and high availability without compromising performance. Linear scalability and proven fault-tolerance on commodity hardware or cloud infrastructure make it the perfect platform for mission-critical data.*

### General informations

This Ansible role is designed to deploy and manage Apache Cassandra database instances but also for bootstraping multi-nodes clusters.

**Table of Contents**

  - [Roles variables](#role-variables)
  - [Examples](#examples)
  - [Install and use this role](#install-and-use-this-role)

**Supported Platforms**

  - Red Hat Enterprise Linux 8.x
  - Ubuntu 22.04

**Supported Cassandre releases**

  - Cassandra 4.0x

**References**

  - Apache Cassandra : https://cassandra.apache.org/

### Role variables

The role variables are available [HERE](docs/variables.md)

### Examples

You can find some configurations examples [HERE](docs/examples.md)

### Install and use this role

* Install the role using the command-line :

  ```shell
  $ ansible-galaxy collection install git+https://github.com/ruskofd/cassandra-role.git
  ```

* Install the collection in your projects using a `requirements.yml` file and `ansible-galaxy` command-line :

  ```YAML
  $ cat requirements.yml
  ---
  roles:
    - name: cassandra
      src: https://github.com/ruskofd/cassandra-role.git
      scm: git
      version: '1.0.0'

  $ ansible-galaxy install-f -r requirements.yml
  ```

* Once the collection is installed, you can use the roles in your playbooks :

  ```yaml
  - name: Install Cassandra server
    hosts: cassandra
    roles:
      - role: cassandra
  ```