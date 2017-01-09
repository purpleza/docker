# Docker file of Gogs Server

## Usage

```bash
docker run --name gogs \
  --hostname gogs \
  --detach \
  --restart always\
  --publish 8081:3000 \
  --volume /data/gogs:/data \
  gogs/gogs
```
