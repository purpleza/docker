# Docker file of Guacamole

## Usage

```bash
docker run --name guacamole \
  --hostname guacamole \
  --detach \
  --restart=always \
  --publish 8083:8080 \
  --link guacd:guacd \
  --link mysql:mysql \
  --env MYSQL_DATABASE=$MYSQL_DATABASE  \
  --env MYSQL_USER=$MYSQL_USER    \
  --env MYSQL_PASSWORD=$MYSQL_PASSWORD \
  guacamole/guacamole
```
