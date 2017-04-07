# Docker file of VNC for X11

## Usage

```bash
docker run --name x11 \
  --hostname x11 \
  --detach \
  --restart=always \
  --publish 5900:5900 \
  purpleza/x11
```
