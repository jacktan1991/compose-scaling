# compose-scaling

## Quick start
- start services with 3 app: `docker-compose up --scale webapp=3`
- check wether LB works: `for i in {1..6}; do curl http://0.0.0.0:8755/api/cat.json; done`
