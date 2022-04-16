# Docker-Compose

Compose es una herramienta para definir y ejecutar aplicaciones Docker de contenedores múltiples. Con Compose, utiliza un archivo YAML para configurar los servicios de su aplicación. Luego, con un solo comando, crea e inicia todos los servicios desde su configuración.

Compose funciona en todos los entornos: producción, puesta en escena, desarrollo, pruebas, así como flujos de trabajo de CI.

Usar Compose es básicamente un proceso de tres pasos:

Defina el entorno de su aplicación con un Dockerfile para que pueda reproducirse en cualquier lugar.

Defina los servicios que componen su aplicación docker-compose.yml para que puedan ejecutarse juntos en un entorno aislado.

Ejecutar docker-compose up y Compose inicia y ejecuta toda su aplicación.

### ¿Cómo instalar Docker Compose?
En Windows, Mac y Linux, los pasos son diferentes

Mac OS: Ya viene instalado dentro de Docker for Mac. Con solo instalar Docker for Mac es suficiente.
https://docs.docker.com/compose/install/

### Version Recomendada
```
docker-compose --version
Docker Compose version v2.3.3
```
### ¿Cómo usar Docker Compose?
¡Aquí viene lo mejor!. Una vez aprendidos los comandos principales, es muy fácil crear recetas y levantar diferentes contenedores, coordinadamente.

### Creamos un docker-compose.yml
Docker Compose, por defecto, busca instrucciones en el archivo docker-compose.yml.

```
docker-compose.yml
```
```
version: '3'
services:
  db:
    container_name: mysql-test
    ports:
      - "3310:3306"
    image: mysql:5.7
    environment:
      - "MYSQL_ROOT_PASSWORD=12345678"
```
“version ‘3’: Los archivos docker-compose.yml son versionados, lo que significa que es muy importante indicar la version de las instrucciones que queremos darle. A medida de que Docker evoluciona, habrá nuevas versiones, pero de todos modos, siempre hay compatabilidad hacia atras, al indicar la version de la receta.

### Comandos Basicos


docker-compose build

Se usa para generar la imagen, basada en las especificaciones del servicio en el docker-compose (y en el Dockerfile)

Se puede especificar qué service del docker-compose buildear, si solo se quiere ejecutar sobre uno.

Ejemplos:
```
docker-compose build   // para buildear todos los services

docker-compose build local //para buildear el service local
```

Luego, con el comando “docker-compose up”, le damos instrucciones a Docker para que cree el contenedor, segun Dockerfile y lo ejecute, con el comando en el Docker-Compose.

Algunas consideraciones:

docker-compose up: da instrucciones a Docker para crear el contendor y ejecutarlo.

docker-compose down: apaga todo los servicios que levantó con docker-compose up.

docker-compose ps: permite ver los contenedores funcionando.

docker-compose exec: permite ejecutar un comando a uno de los servicios levantados de Docker-compose.



