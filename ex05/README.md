## MySQL 도커파일 생성방법

```txt
FROM mysql

ENV MYSQL_USER=jwheo
ENV MYSQL_PASSWORD=jwheo1234
ENV MYSQL_ROOT_PASSWORD=root1234
ENV MYSQL_DATABASE=jwheodb

CMD ["--character-set-server=utf8mb4", "--collation-server=utf8mb4_unicode_ci"]
```

## UTF 8 설정확인
```sh
SHOW VARIABLES LIKE 'character_set_%';
```

```sh
# 실행 명령어
docker build -t mysql-image .
docker run -d --name mysql-container mysql-image
docker exec -it 2a07 bash

# 환경변수 확인
echo $MYSQL_USER

# 볼륨 옵션으로 호스트 폴더 연결해서 실행하는 법
docker run -d -v /$(pwd):/var/lib/mysql -p 3307:3306 --name mysql-container mysql-image

# 이름 있는 볼륨 생성하는 법(도커에서 관리하는)
docker run -d -v mysql-volume:/var/lib/mysql -p 3307:3306 --name mysql-container mysql-image

# 볼륨 목록 확인방법
docker volume list
```
