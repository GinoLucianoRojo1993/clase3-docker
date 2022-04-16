# Recursos Limites Contenedores

Usando Docker, cada contenedor necesitará los mismos recursos para resolver las tareas que tenga que hacer, se activarán y desactivarán procesos internos, y también aparecerán procesos en nuestro equipo real.

```
docker run -d --name mongo mongo
```
En otra sesión podemos dejar corriendo el comando “stats” y veremos los procesos.
```
docker stats
```

```
docker stats mongo
```
```
docker run --help |grep memo
```
```
docker run -d -m "500mb" --name mongo2 mongo
```
```
docker stats mongo2
```

> Uno de los beneficios de “Docker”, procesos en lugar de servidores completos.