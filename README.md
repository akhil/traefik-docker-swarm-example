# traefik-docker-swarm-example

https://dockerswarm.rocks/traefik/

`docker network create --driver=overlay traefik-public`

`export NODE_ID=$(docker info -f '{{.Swarm.NodeID}}')`

`docker node update --label-add traefik-public.traefik-public-certificates=true $NODE_ID`

`export EMAIL=admin@example.com`

`export DOMAIN=traefik.sys.example.com`

`export USERNAME=admin`

`export PASSWORD=changethis`

`export HASHED_PASSWORD=$(openssl passwd -apr1 $PASSWORD)`

`docker stack deploy -c traefik.yml traefik`

`docker stack deploy -c whoami.yml whoami`

