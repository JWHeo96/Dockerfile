# 도커 컴포즈

웹 서버를 예로 들자하면 웹 서버와 DB 두개를 DockerFile로 이미지 생성 후 실행

실행 후 db와 웹서버와의 통신을 위해서는 IP 정보 등 알아야할 요소가 많은데 귀찮아진다.

때문에 도커 컴포즈라는 파일을 작성하게 되면 유기적으로 연결이 되고, 바로 실행까지 해준다.

## 도커 컴포즈 백그라운드 실행법
``` bash
docker-compose up -b
```

## 디비 더미 데이터
``` sql
use rootdb;

create table person (
	id int primary key,
    name varchar(100)
);

insert into person(id, name) values(1, 'jwheo');

select * from person;
```