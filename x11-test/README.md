# Docker file of VNC for X11

## Usage

```bash
docker run --name x11-test \
  --hostname x11-test \
  --rm \
  -it \
  --publish 5900:5900 \
  --publish 6000:6000 \
  purpleza/ubuntu bash
```
