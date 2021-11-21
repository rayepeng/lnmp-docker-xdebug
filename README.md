# lnmp-docker-compose

## mysql 环境

```
docker-compose -f mysql.yml # 密码123456， /tmp/sql/test.db.sql
```


---

Prepare:

1 ubuntu 14.04

2 nginx 1.15.5 (latest)

3 mysql 5.7.23

4 php 7.2 and php 5.6

5 docker 17.04.0-ce (already installed)

6 docker-compose 1.13.0 (already installed)


---

Start:

$ git clone https://github.com/kaka987/lnmp-docker-compose.git

$ cd lnmp-docker-compose

$ mkdir mysql/data

$ docker-compose up -d 

$ chown -R www-data.www-data app/*

$ chmod -R 700 app/*

---

Add local url dns to hosts, such as:

192.168.1.1 hello.in
192.168.1.1 www.hello.in

Request: http://hello.in 

---
