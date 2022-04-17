# Mapear Listar/puertos

con el mapeo de puertos con Docker, esto significa que asignaremos un puerto local de host para apuntarlo a  un puerto de la aplicación que esta corriendo en el contenedor.

```
$ docker pull jenkins/jenkins:latest
```
```
$ docker images | grep jenkins
```
```
$ docker run --help
```
```
$ docker run -d jenkins/jenkins:latest
```
```
$ docker run -d -p 8080:8080 jenkins/jenkins:latest
```
```
$ docker run -d -p 9090:8080 jenkins/jenkins:latest
```

###  Borrar contendor docker ps

$ docker rm -f ID_contenedor

