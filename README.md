# compose-scaling

## Quick start
+ start services with default app instaces: `docker-compose up -d`
  - or you can specific num: `docker-comose up --scale webapp=5`
+ check wether LB works: `for i in {1..6}; do curl http://0.0.0.0:8755/api/cat.json; done`
+ damynic scaling app services: `docker-compose up --scale webapp=10 webapp -d` `docker-compose up --scale webapp=2 webapp -d`
