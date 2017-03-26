![electrum logo](https://cldup.com/J3MGncwehn.png)
### Dockerized Electrum Bitcoin Wallet. This image uses X11 socket.

Requirements:
---
- [Docker](https://github.com/docker/docker)
- xhost (may be needed on some Linux distros)

How to:
---
- Build image  
`git clone https://github.com/loadaverage/electrum.git && cd electrum && docker build -t electrum .`  
**or**  
- Pull image from Docker Registry  
`docker pull loadaverage/electrum`
- Allow access to X server (for some Linux distros)  
`xhost local:electrum`
- Run own Electrum image

 ```bash
docker run --rm \
      -v ~/.electrum:/home/electrum \
      -v ~/.themes:/home/electrum/.themes:ro \
      -v ~/.fonts:/home/electrum/.fonts:ro \
      -v ~/.icons:/home/electrum/.icons:ro \
      -v /usr/share/themes:/usr/share/themes:ro \
      -v /usr/share/fonts:/usr/share/fonts:ro \
      -v /tmp/.X11-unix:/tmp/.X11-unix \
      -e DISPLAY=$DISPLAY electrum
```
- Run Electrum image from Docker Registry  
 ```bash
docker run --rm \
      -v ~/.electrum:/home/electrum \
      -v ~/.themes:/home/electrum/.themes:ro \
      -v ~/.fonts:/home/electrum/.fonts:ro \
      -v ~/.icons:/home/electrum/.icons:ro \
      -v /usr/share/themes:/usr/share/themes:ro \
      -v /usr/share/fonts:/usr/share/fonts:ro \
      -v /tmp/.X11-unix:/tmp/.X11-unix \
      -e DISPLAY=$DISPLAY loadaverage/electrum
```
`NOTE: make sure that "~/.electrum" directory has correct permissions`
