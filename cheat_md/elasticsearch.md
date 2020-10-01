# Elasticsearch

## Set field limit :

```
  curl -XPUT 'http://server:9200/logstash-2020.03.03/_settings' -d '{"index.mapping.total_fields.limit": 3000}'
```


# Disable shard relocation

```
   curl -XPUT localhost:9200/_cluster/settings -d '{"transient":{"cluster.routing.allocation.enable": "none"}}'
```

# Enable shard relocation

```
   curl -XPUT localhost:9200/_cluster/settings -d '{"transient":{"cluster.routing.allocation.enable": "all"}}'
```



# Flush sync

```
   curl -XPOST 'localhost:9200/_flush/synced?pretty'
```


