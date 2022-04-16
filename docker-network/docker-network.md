# Docker Network

Cuando instalamos docker tenemos las siguientes redes predefinidas:
```
# docker network ls
NETWORK ID          NAME                DRIVER              SCOPE
ec77cfd20583        bridge              bridge              local
69bb21378df5        host                host                local
089cc966eaeb        none                null                local
```
Por defecto los contenedores que creamos se conectan a la red de tipo bridge llamada bridge (por defecto el direccionamiento de esta red es 172.17.0.0/16). Los contenedores conectados a esta red que quieren exponer algún puerto al exterior tienen que usar la opción -p para mapear puertos.

## Existen tipos de Networks

- none: no tiene asignado una red

- host: usar la misma ip del servidor real 

- bridge : red standar que se usa en todos los contenedores

Si conecto un contenedor a la red host, el contenedor será accesible usando la misma IP que tu máquina. Por ejemplo:
```
  # docker run -d --name mi_servidor --network host rosross/aplicacionweb:v1
    
  # docker ps
  CONTAINER ID        IMAGE                        COMMAND                  CREATED             STATUS              PORTS               NAMES
  135c742af1ff        roxsross/aplicacionweb:v1   "/usr/sbin/apache2ct…"   3 seconds ago       Up 2 seconds                                  mi_servidor
```
Podemos acceder directamente al puerto 80 del servidor para ver la página web.

La red none no configurará ninguna IP para el contenedor y no tiene acceso a la red externa ni a otros contenedores. Tiene la dirección loopback y se puede usar para ejecutar trabajos por lotes.

```
docker run -d nginx
```
```
docker inspect nombre_contenedor
```
```
docker network ls 
```
```
docker network ls | grep bridge
```
```
docker inspect dca9f66887b6  | grep bridge -C 5
```
