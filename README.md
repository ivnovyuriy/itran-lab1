# itran-lab1

1.1 Nginx + MySQL

docker run --name=nginx -d --network mynet -p 80:80 nginx

![nginx](https://github.com/ivnovyuriy/itran-lab1/blob/789e1bca4d6561c5cc1d398fd27b524251d2bdc5/img/1.png)

![nginx test](https://github.com/ivnovyuriy/itran-lab1/blob/789e1bca4d6561c5cc1d398fd27b524251d2bdc5/img/2.png)

docker volume create --name mysqlvolume

docker network create mynet

docker run --name=mysql -d --network mynet -v mysqlvolume:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=admin -e MYSQL_DATABASE=mydb -p 3306:3306 mysql:latest

![mysql](https://github.com/ivnovyuriy/itran-lab1/blob/789e1bca4d6561c5cc1d398fd27b524251d2bdc5/img/3.png)

docker container ps

OUTPUT:

866e937e5c0f   mysql:latest   
da9e6f424de0   nginx          

docker exec -it 866e937e5c0f mysql -p

SHOW DATABASES;

![mysql output](https://github.com/ivnovyuriy/itran-lab1/blob/789e1bca4d6561c5cc1d398fd27b524251d2bdc5/img/4.png)

CREATE USER 'user1'@'localhost' IDENTIFIED BY 'some_password';

CREATE DATABASE mydb;

![user/db](https://github.com/ivnovyuriy/itran-lab1/blob/789e1bca4d6561c5cc1d398fd27b524251d2bdc5/img/5.png)


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

![Ruby 272](https://github.com/ivnovyuriy/itran-lab1/blob/789e1bca4d6561c5cc1d398fd27b524251d2bdc5/img/6.png)

1.3 Wordpress via docker-compose

cd wordpress/

docker-compose up -d

![wordpress](https://github.com/ivnovyuriy/itran-lab1/blob/789e1bca4d6561c5cc1d398fd27b524251d2bdc5/img/7.png)
