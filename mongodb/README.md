# Docker file of Mongodb Server

## Usage

```bash
docker run --name mongodb \
  --hostname mongodb \
  --detach \
  --restart always \
  --publish 27017:27017  \
  --volume /data/mongodb:/data/db \
  mongo
```
