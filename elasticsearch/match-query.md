## boolean 매치 쿼리
매치쿼리는 검색하려는 필드와 문자열을 포함하는 해시맵. query 문자열안에 공백 구분은 default로  or 검색을 한다. and 검색으로 변경하는 예제는 아래와 같다.
```
curl 'localhost:9200/some-index/some-type/_search' \
    -H 'content-type: application/json' \
    -d '{
        "query": {
            "match": {
               "name": {
                    "query": "Elasticsearch Denver", 
                    "operator": "and"
                }
            }
        }
    }'
```