### 파손된 파일 경로 문제

1. 절대 경로 보다는 상대 경로, 상대 경로보다는 클래스패스를 사용하라.
```java
String filePath = getClass().getResource("category.xml").getFile();
File resource = new File(filePath);
```
2. 특정 OS 종속된 파일 경로를 사용하지 않는다.
3. 파일클래스보다는 스트림으로 대체하라.
   `java.io.File` 보다는 `java.io.OutputStream` or `java.io.ByteArrayOutputStream` 등을 사용하라.
