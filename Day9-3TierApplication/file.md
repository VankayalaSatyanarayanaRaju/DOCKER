How to deploy a 3 tier application
clone the docker webapp from git 
then goto folder --> rm -rf Docker-web ansible compose helm kubernetes

if pom.xml its java+springboot

goto docker-app--> remove multistage 
see the dockerfile 

by seeing docker file to build it we need tar file to get it we need to run maven command and it should be run at pom.xml near means it should run from docker-webapp dir main one--> mvn clean package

now we need to install maven __> better see the latest version and try in gpt 

then mvn clean try after checking the version then we can mvn clean package

 mvn clean package -D skipTests 
check if there is war file in library

we need to copy the target file into docker-app --> cp -r target Docker-app

Then build it from web-app --> docker build -t appimage .

goto docker-db --> 

for db we will have dockerfile if not we have to write see the docker file 

build --> docker build -t dbimage

docker images --> we can see app and db images 

from this image we can create contianers 
rule is 1st need to create for contianer --> docker run -itd --name devopsdb -p 3306:3306 -v mysqlvolume:/var/lib/mysql/ dbimage

docker exec -it devopsdb bash

mysql -u root -p 
give password

we can login to mysql 

CMD-->use accounts;
show tables;
select * from user;
exit  or CRTL+D 2times

now we need to create for app--> goto web-app
docker run -itd --name appcontainer -p 1234:8080 --link devopsdb:mysqlcon appimage

docker exec -it devops bash

docker ps --> and also see logs 

Then copy public ip and use from port no 1234

create a username and password
signup 

check if user created or not in db

mysql -u root -p 

show databases;
use accouts;
show tables;
select * from user;
we can see the user which we created and it is updated in db


Now we can write the compose file to it 