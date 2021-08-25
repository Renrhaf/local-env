# Local environment

Local dev environment using Docker and Traefik (v2)

## Start traefik

```
cd traefik
docker network create traefik_net
docker-compose up -d
```

## Start all shared containers

```
docker network create postgres_net
docker network create mariadb_net
docker network create redis_net
docker network create elk_net
docker-compose -f docker-compose-postgres.yml up -d
docker-compose -f docker-compose-mariadb.yml up -d
docker-compose -f docker-compose-redis.yml up -d
docker-compose -f docker-compose-adminer.yml up -d
docker-compose -f docker-compose-mailhog.yml up -d
```

## Start ELK

```
cd elk
docker network create elk_net
docker-compose up -d
```
