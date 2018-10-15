## Term Query Example
일치하는 단어 검색
```
curl 'localhost:9200/some-index/some-type/_search' \ 
    -H 'content-type: application/json' \
    -d '{
        "query": {
            "term": {
                "tags": "elasticsearch"
            }
        },
        "_source": ["name", "tags"]
    }'
```

## Term Filter Query Example
일치하는 단어 필터로 검색
```
curl 'localhost:9200/some-index/some-type/_search' \
    -H 'content-type: application/json' \
    -d '{
        "query": {
            "bool": {
                "must": [
                    { "match_all": {}}
                ],
                "filter": {
                    "term": {
                        "tags": "elasticsearch"
                    }
                }
            }
        }
    }'
```
## Terms Query Example
일치하는 단어 여러개 검색
```
curl 'localhost:9200/some-index/some-type/_search' \
    -H 'content-type: application/json' \
    -d '{
        "query": {
            "terms": {
                "tags": ["jvm", "hadoop"]
            }
        },
        "_source": ["name", "tags"]
    }'
```