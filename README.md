# itran-lab1

1.1 Nginx + MySQL

docker run --name=nginx -d --network mynet -p 80:80 nginx

docker volume create --name mysqlvolume

docker network create mynet

docker run --name=mysql -d --network mynet -v mysqlvolume:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=admin -e MYSQL_DATABASE=mydb -p 3306:3306 mysql:latest 

docker container ps

OUTPUT:

866e937e5c0f   mysql:latest   
da9e6f424de0   nginx          

docker exec -it 866e937e5c0f mysql -p

SHOW DATABASES;

OUTPUT:

+--------------------+
| Database           |
+--------------------+
| information_schema |
| mydb               |
| mysql              |
| performance_schema |
| sys                |
+--------------------+

CREATE USER 'user1'@'localhost' IDENTIFIED BY 'some_password';

CREATE DATABASE mydb;


1.2 Ruby + Ubuntu 20.04 Dockerfile

Installing

docker build -t ruby272:v1 .

irb(main):001:0> RUBY_VERSION
=> "2.7.2"
irb(main):001:0> exit

docker run --rm -it ruby272:v1

docker exec -it 3949bf052601 bash

ruby -v

cat /etc/issue

1.3 Wordpress via docker-compose

cd wordpress/

docker-compose up -d



