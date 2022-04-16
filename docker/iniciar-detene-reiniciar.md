# Iniciar - Detener - Reiniciar
```
docker ps 
```
```
docker run -d -p 8080:8080 jenkins:2.60.3
```

### renonbrar contenedor
```
docker rename magical_maxwell jenkins-test
```

### stopear contenedor
```
docker stop nombre_contenedor
```

### iniciar contenedor
```
docker stop nombre_contenedor
```
### Entrar dentro del contenedor
```
docker exec -ti nombre_contenedor bash 
```
### Entrar contenedor con usuario root
```
docker exec -u root -ti nombre_contenedor bash 
```
```
$ docker exec -ti nombre_contenedor sh

cat /var/jenkins_home/secrets/initialAdminPassword
```
