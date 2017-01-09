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
  --env MYSQL_DATABASE=$db  \
  --env MYSQL_USER=$dbUser    \
  --env MYSQL_PASSWORD=$dbPassword \
  guacamole/guacamole
```
