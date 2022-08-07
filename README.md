[![redteamcafe.com](https://github.com/redteamcafe/docker-temp/raw/main/redteamcafe-logo.png)](https://redteamcafe.com)

Red Team Cafe is an organization dedicated to information technology and security.

We are proud to bring you one of our docker containers!

# [redteamcafe/docker-responder](https://github.com/redteamcafe/docker-responder)

[![Responder](https://raw.githubusercontent.com/redteamcafe/docker-responder/main/_images/Responder-logo.png)](https://github.com/lgandx/Responder)

## About this Build

* 

Responder is an LLMNR, NBT-NS and MDNS poisoner.

Currently supported:
* x86-64

# Deployment

## Docker Compose

```
docker run -it -d --net host --name=responder redteamcafe/responder
```

## Docker CLI

*Prefered Method*

```
version: '3'

services:
  pialert:
    image: redteamcafe/responder:latest
    container_name: responder
    environment:
      PUID: 1000
      PGID: 1000
    volumes:
      - /responder/logs
#    ports:
#      - 8080:80
    network_mode: "host"
    stdin_open: true # docker run -i
    tty: true        # docker run -t
    restart: unless-stopped
```
## Parameters
| Parameter | Function |
| :----: | --- |
| `-p 8080:80` ||
| `-e PUID=1000` | set UserID |
| `-e PGID=1000` | set GroupID |
| `-v ./responder/logs:/usr/share/responder/logs` | location where pialert data is stored |


# Future Contributions and Features
*


