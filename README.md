# Dockerizing-Spring-Boot_Microservices

## Postman Collection for Explore California API's url
[Explore California Postman API Collection](https://www.getpostman.com/collections/98182b1b38716f156bfc)

## springdoc-openapi Documentation
[springdoc-openapi](https://springdoc.org/)

Final Product requires External MySql Database.
Install Docker For Mac/Windows/Linux

#### Docker Commands
##### Start MySql Container (downloads image if not found)
``
docker run  --detach   --name ec-mysql -p 6604:3306 -e MYSQL_ROOT_PASSWORD=password -e MYSQL_DATABASE=explorecali -e MYSQL_USER=cali_user -e MYSQL_PASSWORD=cali_pass -d mysql
``

##### view all images
``
docker images
``

##### view all containers (running or not)
``
docker ps -a
``
##### Interact with Database (link to ec-mysql container) with mysql client
``
docker run -it --link ec-mysql:mysql --rm mysql sh -c 'exec mysql -h"$MYSQL_PORT_3306_TCP_ADDR" -P"$MYSQL_PORT_3306_TCP_PORT" -uroot -p"$MYSQL_ENV_MYSQL_ROOT_PASSWORD"'
``
##### Stop ec-mysql container
``
docker stop ec-mysql
``
##### (ReStart) ec-mysql container
``
docker start ec-mysql
``
##### Remove ec-mysql container (must stop it first)
``
docker rm ec-mysql
``
##### Remove image (must stop and remove container first)
``
docker rmi mysql:latest
``