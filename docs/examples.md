Examples
--------

#### Create a simple 3-nodes cluster in a single datacenter

```YAML
### Global vars for all cluster members
cassandra_cluster_name: "Ansible Cluster"
cassandra_num_tokens: 256
cassandra_endpoint_snitch: SimpleSnitch

# You need to define seed nodes for cluster bootstrap (choose at least 2 seed nodes in this configuration)
cassandra_seed_nodes: [ "10.0.122.196:7000", "10.0.122.195:7000" ]

### Node 1
cassandra_listen_address: "10.0.122.196"
cassandra_rpc_address: "10.0.122.196"

### Node 2
cassandra_listen_address: "10.0.122.195"
cassandra_rpc_address: "10.0.122.195"

### Node 3
cassandra_listen_address: "10.0.122.194"
cassandra_rpc_address: "10.0.122.194"
```