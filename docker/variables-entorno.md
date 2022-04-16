# variables entorno

Una variable de entorno según la wikipedia — es un valor con nombre dinámico que puede afectar la forma en que los procesos en ejecución se comportarán en una computadora. Son parte del entorno en el que se ejecuta un proceso —. En otras palabras, imaginemos estamos creando un contenedor que despliegue una imagen con base de datos como MySQL o Postgres, si vamos a las documentaciones oficiales notaremos que para crear una contraseña o un nombre para una base de datos debemos enviarle unos parámetros mediante variables con nuestros valores, pues éstas variables son argumentos la imagen de docker recibirá a través de las variables de entorno.

> Entonces es un argumento que "recibe" el valor del parámetro por parte de las variables de entorno para ejecutar una rutina, o un proceso.


Ejemplo:

```
$ docker run -e MYSQL_ROOT_PASSWORD=mi-contraseña mysql
````

Se debe contar con un [DockerFile](https://raw.githubusercontent.com/roxsross/clase2-automation/master/docker/Dockerfile)

### Contruccion de la imagen del contenedor

```
$ docker build -t env .  
```
### Iniciar Contenedor
```
$ docker run -it  env
```
### Entramos en el Contenedor

```
$ docker exec -ti  env  bash

[root@655f96a23e5b /]# echo $prueba
```
### Configuramos Variable de entorno
```
$ docker run -dti -e "prueba1=4321" --name environments env
$ docker exec -ti  environments  bash
printenv
```