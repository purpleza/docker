# Docker file of Proxy Service

## Usage

```bash
docker run --name proxy \
  --hostname proxy \
  --detach \
  --restart=always \
  -p 9001:9001 \
  purpleza/proxy
```
