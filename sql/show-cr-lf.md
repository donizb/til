# SELECT 시 내용에 CR LF 표시(찾기)
```
select replace(replace(content, char(10), 'LF'), chr(13), 'CR') content from tbl;
```
