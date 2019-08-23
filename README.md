# compose-scaling

## Pre start
### init swarm
docker swarm init

## Quick start
+ start services with default app instaces: `docker stack deploy -c docker-stack.yml compose-scaling`
+ check wether LB works: `for i in {1..6}; do curl http://0.0.0.0:8755/api/cat.json; done`
+ damynic scaling app services: `docker service scale compose-scaling_webapp=10`
