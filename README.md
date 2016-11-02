# docker-sparklify
Distributed triplestore setup (Sparqlify+Hive) inside docker environment.

## How to run
Before proceeding to start the next stage make sure that the services from the previous stage is fully operational (use ```docker logs``` command to check).
```
  docker network create sparklify
  docker-compose -f docker-compose-stage1.yml up -d
  docker-compose -f docker-compose-stage2.yml up -d
  docker-compose -f docker-compose-stage3.yml up -d
```

Run beeline client:
```
docker exec -it hive-server /opt/hive/bin/beeline -u jdbc:hive2://localhost:10000
```
