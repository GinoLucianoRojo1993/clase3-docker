# Docker Volumes

debe considerar si realmente necesita datos de Docker almacenados en el servidor. Para muchas aplicaciones, el uso de un almacén de datos remoto externo como Amazon S3 o una base de datos externa es suficiente para almacenar los datos que usan sin vincularlos al servidor frontend.


¿Cómo los usas?
Puede crear un nuevo volumen desde la línea de comando con el siguiente comando:
```
docker volume create nginx-config
````

Y luego, cuando vaya a ejecutar su contenedor Docker, conéctelo al destino en el contenedor con el --mount bandera:
```
docker run -d 
--name devtest 
--mount source=nginx-config,target=/etc/nginx 
nginx:latest
```

Si tu corres docker inspect <name>, verá el volumen que se enumera a continuación Mounts sección.

```
mkdir data
mkdir -p data/mysql

docker run -d --name db2 -p 3307:3306 -e "MYSQL_ROOT_PASSWORD=12345678" -v /Users/rossanasuarez/295devops/clase-3/clase3-docker/docker-volumes/data/mysql:/var/mysql mysql
````
```
cd /opt
mkdir mysql

docker run -d --name db -p 3306:3306 -e "MYSQL_ROOT_PASSWORD=12345678" -v /opt/mysql/:/var/lib/mysql mysql

```
```
jenkins ....

docker run -d --name jenkins2 -p 9090:8080 -v /Users/rossanasuarez/295devops/clase-3/clase3-docker/docker-volumes/data/jenkins/:/var/jenkins_home jenkins:2.60.3 

/var/jenkins_home/secrets/initialAdminPassword

```