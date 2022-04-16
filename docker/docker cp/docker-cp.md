
# Copiar archivos en Contenedor
```
docker cp
```
```
docker run -d --name apache -p 80:80 httpd

echo ":)" > index.html 
```
```
docker cp index.html apache:/tmp

docker exec -ti apache bash
```
```
docker cp index.html apache:/usr/local/apache2/htdocs/index.html
```