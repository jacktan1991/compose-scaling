# compose-scaling

## Quick start
+ start services with default app instaces: `docker-compose up -d`
  - or you can specific num: `docker-comose up --scale webapp=5`
+ check wether LB works: `for i in {1..6}; do curl http://0.0.0.0:8755/api/cat.json; done`
+ damynic scaling app services: `docker-compose up --scale webapp=10 webapp -d` `docker-compose up --scale webapp=2 webapp -d`


### net work error
if Docker Engine use overlay driver for network, you will meet error:

```
Creating network "compose-scaling_default" with the default driver
ERROR: could not find an available, non-overlapping IPv4 address pool among the defaults to assign to the network
```

"non-overlapping IPv4 address" here indicates you should specify **bridge driver** explicitly for `docker-compose up`

refs: https://docs.docker.com/compose/compose-file/compose-file-v2/#driver-1

_overlay driver is only for Swarm mode, for single host docker-compose can not use it_
