# Sample `docker-compose.yml`

```yml
version: '3.4'

services:
  tgdante2:
    image: docker.pltrm.net/tgdante2
    networks:
      - traefik_net
    environment:
      - "PORT=1080"
      - "USER=<username>"
      - "PASS=<password>"
    ports:
      - target: 1080
        published: 1080
        protocol: tcp
        mode: host
    deploy:
      replicas: 1
      placement:
        constraints:
          - node.role==manager

networks:
  traefik_net:
    external: true
```
