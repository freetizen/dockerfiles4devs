# MariaDB

[MariaDB](http://mariadb.org) is one of the most popular database servers in the world. It’s made by the original developers of MySQL and guaranteed to stay open source.

[![](https://images.microbadger.com/badges/image/freetizen/mariadb.svg)](https://microbadger.com/images/freetizen/mariadb "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/freetizen/mariadb.svg)](https://microbadger.com/images/freetizen/mariadb "Get your own version badge on microbadger.com")

## Usage

```
docker run -it -p 3306:3306 -v /host/dir/for/db:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=supersecret -e MYSQL_DATABASE=mydb -e MYSQL_USER=myuser -e MYSQL_PASSWORD=secret --name mariadb freetizen/mariadb
```

## Configuration example with docker-compose

```
# docker-compose.yml
version: '2'

services:
  mariadb:
    image: freetizen/mariadb
    ports:
      - 0.0.0.0:3306:3306
    environment:
      - MYSQL_ROOT_PASSWORD=supersecret
      - MYSQL_DATABASE=mydb
      - MYSQL_USER=myuser
      - MYSQL_PASSWORD=secret
```
