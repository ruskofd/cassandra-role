Role Variables
--------------

#### General

| Name                              | Default                      | Description                                                      |
| :-------------------------------- | :--------------------------- | :--------------------------------------------------------------- |
| `cassandra_version`               | `4.0.4`                      | Defines the version of Cassandra to install                      |
| `cassandra_user`                  | `cassandra`                  | Defines the user to create to run Cassandra                      |
| `cassandra_group`                 | `cassandra`                  | Defines the user group to create to run Cassandra                |
| `cassandra_java_pkg_install`      | `true`                       | If set to `true`, install Java Runtime (OpenJDK) required to run Cassandra |
| `cassandra_java_pkg_version`      | see [vars](../vars/)         | Defines to the major version of Java Runtime to install          |
| `cassandra_python_pkg_install`    | `true`                       | If set to `true`, install Python3 runtime required for the `cqlsh` utility |
| `cassandra_env_file`              | see [vars](../vars/)         | Defines where the Cassandra service environment file is stored on disk |

#### Configurations

| Name                              | Default                      | Description                                                      |
| :-------------------------------- | :--------------------------- | :--------------------------------------------------------------- |
| `cassandra_cluster_name`          | `Test Cluster`               | Defines the name of the cluster. This is mainly used to prevent machines in one logical cluster from joining another |
| `cassandra_num_tokens`            | `16`                         | Defines the number of tokens randomly assigned to this node on the ring |
| `cassandra_authenticator_backend` | `AllowAllAuthenticator`      | Defines the authentication backend used to identify users        |
| `cassandra_autorizer_backend`     | `AllowAllAuthorizer`         | Defines the authorization backend used to limit access/provide permissions |
| `cassandra_network_authorizer`    | `AllowAllNetworkAuthorizer`  | Defines the network authorization backend used to restrict user access to certain DCs |
| `cassandra_data_dirs`             | `["/var/lib/cassandra"]`   | Defines the directories where Cassandra should store data on disk. If multiple directories are specified, Cassandra will spread data evenly across them by partitioning the token ranges |
| `cassandra_commitlog_dir`         | `/var/lib/cassandra/commitlog`| Defines the directory where Cassandra should store commit logs on disk |
| `cassandra_saved_caches_dir`      | `/var/lib/cassandra/saved_cachedata`| Defines the directory where Cassandra should store saved cachedata on disk |
| `cassandra_hints_dir`             | `/var/lib/cassandra/hints`   | Defines the directory where Cassandra should store hints |
| `cassandra_log_dir`               | `/var/log/cassandra`         | Defines the directory where Cassandra should write his logs on disk |
| `cassandra_disk_failure_policy`   | `stop`                       | Defines the policy to use when a data disk failure occured on the node |
| `cassandra_commit_failure_policy` | `stop`                       | Defines the policy to use when a commitlog disk failure occured on the node |
| `cassandra_commitlog_sync`        | `periodic`                   | Defines the sync mode for commitlogs                             |
| `cassandra_commitlog_sync_period` | `10000`                      | Defines the sync period for commitlogs sync                      |
| `cassandra_seed_nodes`            | `["127.0.0.1:7000"]`         | Defines the cluster seed nodes                                   |
| `cassandra_concurrent_reads`      | `32`                         | Defines the concurrent reads allowed when workloads use more data than can fit in memory | 
| `cassandra_concurrent_writes`     | `32`                         | Defines the concurrent writes allowed when workloads use more data than can fit in memory |
| `cassandra_disk_optimization_strategy`| `ssd`                    | Defines the strategy used to optimize reads on disk              |
| `cassandra_storage_port`          | `7000`                       | Defines the TCP port used for commands and data                  |
| `cassandra_listen_address`        | `localhost`                  | Defines the address or interface to bind to and tell other Cassandra nodes to connect to |
| `cassandra_native_transport_enabled`| `true`                     | If set to `true`, enable the native transport server             |
| `cassandra_native_transport_port` | `9042`                       | Defines the port for the CQL native transport to listen for clients on |
| `cassandra_rpc_address`           | `localhost`                  | Defines the address to bind the native transport server to       |
| `cassandra_incremental_backups_enabled`| `false`                 | If set the `true`, enable incremental backups. Cassandra create a hard link to each SSTable flushed or streamed locally in a backups/ subdirectory of the keyspace data |
| `cassandra_read_request_timeout`  | `5000`                       | Defines how long the coordinator should wait for read operations to complete |
| `cassandra_range_request_timeout` | `10000`                      | Defines how long the coordinator should wait for seq or index scans to complete |
| `cassandra_write_request_timeout` | `2000`                       | Defines how long the coordinator should wait for writes to complete |
| `cassandra_counter_write_request_timeout` | `5000`               | Defines how long the coordinator should wait for counter writes to complete |
| `cassandra_cas_contention_timeout` | `1000`                      | Defines how long a coordinator should continue to retry a CAS operation that contends with other proposals for the same row
| `cassandra_truncate_request_timeout`| `60000`                    | Defines how long the coordinator should wait for truncates to complete |
| `cassandra_misc_request_timeout` | `10000`                       | Defines the default timeout for other miscellaneous operations   |
| `cassandra_slow_query_log_timeout` | `500`                       | Defines how long before a node logs slow queries                 |
| `cassandra_cross_node_timeout_enabled`| `true`                   | If set to `true`, enable operation timeout information exchange between nodes to accurately measure request timeouts.
| `cassandra_endpoint_snitch`       | `SimpleSnitch`               | Defines the Endpoint Snitch to use                               |
| `cassandra_internode_compression` | `dc`                         | Defines the mode of inter-node compression traffic               |
| `cassandra_rackdc_dc_name`        | `dc1`                        | Defines the DC name for the node                                 |
| `cassandra_rackdc_rack_name`      | `rack1`                      | Defines the rack name for the node                               |
