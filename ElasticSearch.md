# Elasticsearch

## 

Creation index:
```
PUT data0
{"settings":{"index":{"number_of_shards":2,"number_of_replicas":0}}}
```

Modif index:
```
PUT data0/_settings
{ "index" : {
"number_of_replicas": 6,
"refresh_interval": "30s"
}}
```

Creation d'alias:
```
POST /_aliases
{
    "actions" : [
        { "add" : { "index" : "test1", "alias" : "alias1" } },
        { "add" : { "index" : "test2", "alias" : "alias1" } }
    ]
}
```
















```
