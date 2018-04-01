# Databases On Docker 
### Prerequisite
* Docker


## Cassandra
Building Cassandra Database on docker. Docker compose build three nodes, cassandra0 (main seed node), cassandra1 and cassandra2

### Run Cassandra container
Navigate to ./DBsOnDocker/cassandra folder.
Start docker compose
```console
    $ docker-compose -f ./Cassandra/docker-compose.yml up -d
```

## Microsoft SQL Server
Build Microsoft SQL Server on docker.
### Run MSSQL Server container
```console
    docker-compose -f ./MSSQLServer/docker-compose.yml up -d
```
