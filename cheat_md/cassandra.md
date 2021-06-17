# Cassandra tricks

## Usefull tools to set correct replication strategy and factor : 

  - https://github.com/DataStax-Toolkit/cassandra-dse-helper-scripts
    e/g: ``` ./adjust-keyspaces.sh -c "-u cassandra $(hostname -i) -p ********" [keyspace1] [keyspace2] ... ```
    If no keyspace is specified, the adjustment will be made on system keyspaces

## Nodetool :

Nodetool is the cli tool to interact with the cluster and node

Global status :

```
  nodetool status
```


## Usefull requests ( on cqlsh )

```
  DESCRIBE keyspaces;
  DESCRIBE <keyspace_name>;
  
  # To list all user and their privileges :
  LIST ALL;
```
