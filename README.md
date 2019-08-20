# compose-scaling

## Pre start
pre create external network use `docker network`

- `docker network create compose-scaling --subnet 172.24.24.0/24`
- rm this external network after compose down: `docker network rm compose-scaling`

### why use external network
to resolev err when docker-compose up:

```
Creating network "compose-scaling_default" with the default driver
ERROR: could not find an available, non-overlapping IPv4 address pool among the defaults to assign to the network
```

## Quick start
+ start services with default app instaces: `docker-compose up -d`
  - or you can specific num: `docker-comose up --scale webapp=5`
+ check wether LB works: `for i in {1..6}; do curl http://0.0.0.0:8755/api/cat.json; done`
+ damynic scaling app services: `docker-compose up --scale webapp=10 webapp -d` `docker-compose up --scale webapp=2 webapp -d`
