# Elasticsearch

## Set field limit :

```
  curl -XPUT 'http://server:9200/logstash-2020.03.03/_settings' -d '{"index.mapping.total_fields.limit": 3000}'
```
