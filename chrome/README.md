# Docker file of google chrome browser

## Usage

```bash
docker run --name chrome \
  --hostname chrome \
  --detach \
  --restart=always \
  -e DISPLAY=${hostIp}:0 \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  -v /data/chrome:/data \
  purpleza/chrome
```
