## wget -O 옵션 사용법

파일명을 다르게하여 다운로드 하고 싶을 때 아래와 같이 하면 된다.
```
wget -O example.txt http://example.com/example-20180626.txt
```

파일명 대신 `-`를 사용하면 표준 출력으로 output한다. 이를 통해 쉘스크립트 실행등을 응용할 수 있다.
```
wget -qO - http://example.com/example.sh | bash
```

여기서 `-q`옵션은 wget의 진행되는 내용들을 없애는 역할을 한다.
