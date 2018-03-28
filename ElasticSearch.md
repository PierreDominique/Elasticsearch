# Elasticsearch

## TP 

* Creation index:
```
PUT data0
{"settings":{"index":{"number_of_shards":2,"number_of_replicas":0}}}
```

* Modif index:
```
PUT data0/_settings
{ "index" : {
"number_of_replicas": 6,
"refresh_interval": "30s"
}}
```

* Creation d'alias:
```
POST /_aliases
{
    "actions" : [
        { "add" : { "index" : "test1", "alias" : "alias1" } },
        { "add" : { "index" : "test2", "alias" : "alias1" } }
    ]
}
```

* Suppression de tout :
```
DELETE /_all
```

* Mapping :
```
{
  "mappings": {
    "produit": {
      "properties": {
        "code": {
          "type": "string",
          "index": "not_analyzed",
          "store": true
        },
        "name": {
          "properties": {
            "nom": {
              "type": "string",
              "index": "analyzed",
              "store": "true"
            },
            "original": {
              "type": "string",
              "index": "not_analyzed",
              "store": "true"
            }
          }
        },
        "echelle": {
          "type": "string",
          "index": "not_analyzed"
        },
        "fournisseur": {
          "type": "string",
          "index": "analyzed",
          "null_value": "unknow",
          "store": true
        },
        "stock": {
          "type": "integer"
        },
        "prix": {
          "type": "float"
        },
        "devise": {
          "type": "string",
          "index": "not_analyzed"
        }
      }
    }
  }
}
```
* vérification de l'existance 
GET /data/_mapping

* à roujter
"include_in_all": true, 





