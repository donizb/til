## 리눅스 tar.gz 압축/해제 명령어

확장자 tar는 압축없이 여러 파일들은 한 파일로 묶은 것(archive)을 의미하고 tar.gz는 아카이빙 한 tar 파일을 gunzip으로 압축한 것을 말한다.



### 압축하기

```
tar -c [options] [<file> | <dir>]
```

압축시 기본적으로 `-c`옵션을 사용하며 정확히는 압축이 아니라 단순히 하나의 파일로 묶기만 한다. 추가 옵션으로 `-z` 를 사용하게 되면 tar로 묶은 것을 gunzip으로 압축한다. (추가로 bzip2/xz/lzma형식의 압축을 사용하고 싶다면 `-j`,`-J`,`--lzma` 옵션을 사용하면 된다.) 압축과 압축해제시 `-f` 옵션과 `-v` 옵션을 함께 많이 쓰이는데 `-f` 는 아카이브의 이름을 지정하는 것이므로 꼭 명시해야 한다. `-v` 옵션은 아카이브에 추가되거나 풀리고 있는 파일들의 진행사항들을 알려준다.

#### 예제 

- exmple폴더의 내용을 example.tar로 묶는다.

```
tar -cf example.tar example/
```



- example폴더의 내용을 진행사항을 화면에 표시하며 example.tar로 묶는다.

```
tar -cvf example.tar example/
```



- example폴더의 내용을 진행사항을 화면에 표시하며 tar로 묶고 gunzip으로 압축한다.

```
tar -cvzf example.tar.gz example/
```



### 압축풀기

```
tar -x [options] 
```

압축을 풀때는 `-x` 옵션을 사용하여 압축을 푼다. 이것 역시 마찬가지로 tar로 묶은 파일을 말하며 gunzip으로 된 압축파일을 풀때에는 압축할때와 마찬가지로 `-z` 를 추가해야 한다. 



#### 예제

- example.tar로 묶어진 파일을 푼다.

  ``` 
  tar -xf example.tar
  ```

- example.tar  파일을 진행사항을 화면에 표시하며 푼다.

  ```
  tar -xvf example.tar
  ```

- example.tar.gz으로 압축된 파일을 진행사항을 화면에 표시하며 푼다.

  ```
  tar -xvzf example.tar
  ```

  



### 옵션 정리

- -f : 원하는 압축 파일명
- -c : 지정한 파일을 tar로 묶음
- -x : 압축 해제
- -r : 묶인 tar에 새 파일을 추가
- -t : tar 안에 들어있는 파일을 목록으로 표시
- -v : 압축 및 해제 과정을 상세한 메시지로 출력
- -z : 묶은 tar를 gzip으로 압축
- -j : 묶은 tar를 bzip2로 압축
- -J : 묶은 tar를 xz로 압축