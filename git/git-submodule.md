## 서브모듈
git 디렉토리내에서 다른 git을 참조해야한다면 submodule을 쓸 수 있다
```
git submodule add https://github.com/something/submodule.git
```

그러면 git 디렉토리에 .gitmodules파일이 생성되면서 submodule 정보가 들어간다. 이 파일만 있으면 아래 명령어를 통해 서브모듈의 내용을 가져올 수 있다. (부모 저장소를  git clone을 하면 submodule 내용을 함께 가져오지 못한다. 빈폴더만 생성함. )
```
git submodule init
git submodule update
```

부모 저장소를 git clone 할 때 submodule내용도 함께 가져오고 싶다면 `--recursive` 옵션을 사용하면 된다. 
```
git clone --recursive [원격주소]
```
