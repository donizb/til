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

## phrase 매치 쿼리
Enterprise search London get-together를 검색하고자 하나 생각나는 단어가 Enterprise  London 이라면 phrase 매치쿼리를 사용할 수 있다.
slop은 구문 내 토큰 사이의 거리를 표현하는 수치 값
```
curl 'localhost:9200/get-together/_doc/_search' \
    -H 'content-type: application/json' \
    -d '{
        "query": {
            "match_phrase": {
                "name": {
                    "query": "enterprise london",
                    "slop": 1
                }
            }
        }
    }'
```