## Bool Query
must는 일치. should는 있거나 없거나. (minimum_should_match값에 따라 일치 갯수 여부 달라짐) must_not은 불일치.
```
curl 'localhost:9200/get-together/_search' \
    -H 'Content-Type: application/json' \
    -d '{
        "query": {
            "bool": {
                "must": [
                    {
                        "term": {
                            "attendees": "david"
                        }
                    }
                ],
                "should": [
                    {
                        "term": {
                            "attendees": "clint"
                        }
                    },
                    {
                        "term": {
                            "attendees": "andy"
                        }
                    }
                ],
                "must_not": [
                    {
                        "range": {
                            "date": {
                                "lt": "2013-06-30T00:00"
                            }
                        }
                    }
                ],
                "minimum_should_match": 1
            }
        }
    }'
```
## Bool Filter Query
위 Bool Query에 filter 결합.

```
curl 'localhost:9200/get-together/_search' \
    -H 'Content-Type: application/json' \
    -d '{
        "query": {
            "bool": {
                "must": {
                    "match_all": {}
                },
                "filter": {
                    "term": {
                        "attendees": "david"
                    }
                }
            }
        }
    }'
```