# Docker file of eclipse

## Usage

```bash
docker run --name che \
  --hostname che \
  --detach \
  --restart always \
  --publish 8084:8080 \
  --volume /var/run/docker.sock:/var/run/docker.sock \
  --volume /data/che:/data \
  -e CHE_IP=192.168.21.201 \
  eclipse/che-server
```
