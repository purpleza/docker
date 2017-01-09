# Docker file of MySQL Database Server

## Usage

### Run Server

```bash
docker run --name mysql \
  --hostname mysql \
  --detach \
  --restart=always \
  --volume /data/mysql/config:/etc/mysql/conf.d \
  --volume /data/mysql/data:/var/lib/mysql \
  mysql
```

### Run Client

```bash
docker run --link mysql:mysql \
  --rm -it \
  -v $(pwd):/data \
  mysql \
  mysql -h mysql -u root -p
```