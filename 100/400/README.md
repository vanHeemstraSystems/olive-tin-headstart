# 400 - Installation using Docker Compose

Docker compose is a popular way to define multi-container applications using a infrastructure as code approach.

If you personally prefer to use ```docker compose```, then here is a sample to get you started;

```
version: "3.8"
services:
  olivetin:
    container_name: olivetin
    image: jamesread/olivetin
    volumes:
      - /docker/olivetin:/config # replace host path or volume as needed
    ports:
      - "1337:1337"
    restart: unless-stopped

networks:
  web: # should match the network defined under the container's networks
  section
      external: true
```
containers/olivetin/docker-compose.yml

You should be able to browse to http://yourserver:1337 (or similar) to get to the web interface.

If you see the OliveTin page popup in your browser, you can jump to the [configuration section](https://docs.olivetin.app/config.html) as the next step.

## 100 - Using Traefik with Docker Compose (and HTTPS)

Traefik is a popular reverse proxy that seems to be used a lot in people’s Docker compose setups.

Adjust the ```docker-compose.yml``` example above to include the following labels;

```
...
    labels:
      - traefik.http.routers.olivetin.rule=Host(`run.your.domain`)
      - traefik.http.routers.olivetin.tls.certresolver=lets-encrypt
...
```
