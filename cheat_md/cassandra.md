# Cassandra tricks

## Usefull tools to set correct replication strategy and factor : 

  - https://github.com/DataStax-Toolkit/cassandra-dse-helper-scripts
    e/g: ``` ./adjust-keyspaces.sh -c "-u cassandra $(hostname -i) -p ********" [keyspace1] [keyspace2] ... ```
    If no keyspace is specified, the adjustment will be made on system keyspaces

## Nodetool :

Nodetool is the cli tool to interact with the cluster and node



```bash
 nodetool status # Global status 
 nodetool repair -pr <keyspace_name> # To enforce the rule of replication
```


## Usefull requests ( on cqlsh )

```
  DESCRIBE keyspaces;
  DESCRIBE <keyspace_name>;
  
  # To list all user and their privileges :
  LIST ALL;
```

## Good to know :

- Most of times you must use `NetworkTopologyStrategy` :
  https://docs.datastax.com/en/cassandra-oss/3.x/cassandra/architecture/archDataDistributeReplication.html
- Replica factor value will set the number of occurrences of records ( unlike Elasticsearch )
- Modifying replica factor will require to run `nodetool repair -pr <keyspace_name>`

