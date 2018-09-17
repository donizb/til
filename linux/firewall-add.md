## 방화벽 포트 추가하는 방법(CentOS 7)

### 포트 추가
```
firewall-cmd --permanent --zone=public --add-port=80/tcp
firewall-cmd --reload
```

### 포트 제거
```
firewall-cmd --permanent --zone=public --remove-port=80/tcp
firewall-cmd --reload
```
