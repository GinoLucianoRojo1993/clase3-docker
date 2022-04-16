
# Testeando MySQL en Ubuntu

```
docker run --rm -ti ubuntu bash
```
### Instalamos dentro del contenedor
```
apt-get update
apt install mysql-server mysql-client
```
Luego nos conectamos a la BD
```
mysql -u root -p
```

### Si da error....

```
apt install nano
nano /etc/mysql/mysql.conf.d/mysqld.cnf
etc/init.d/mysql restart
```

## Ahora testearemos una imagen mysql de dockerhub

```
docker pull mysql
```
```
docker run -d --name db1 -p 3306:3306 -e "MYSQL_ROOT_PASSWORD=12345678" mysql
```
```
docker logs nombre_contenedor
```
```
mysql -u root -h 127.0.0.1 -p12345678
```