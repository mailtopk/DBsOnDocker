
# Cassandra Container
Building Cassandra Database on docker. Docker compose build three nodes, cassandra0 (main seed node), cassandra1 and cassandra2.
*Note* - Cassandra need more memory to run three nodes, increase the memory in  Docker prefernces to 6g.

### Run compose file
Navigate to cd DBsOnDocker/cassandra directroy.
Start docker compose
```console
    docker-compose up -d
```

### Verify the containers are up and running 
```console
    docker ps --format "table {{.ID}}\t {{.Names}}\t {{.Ports}}\t {{.Status}}"
```

### Expected output, List of nodes
```console
CONTAINER ID         NAMES               PORTS                                                        STATUS
7fc0a0a1ac7d         cassandra1          7000-7001/tcp, 7199/tcp, 9160/tcp, 0.0.0.0:9042->9042/tcp    Up 41 minutes
80c338c79a7b         cassandra0          7000-7001/tcp, 7199/tcp, 9042/tcp, 9160/tcp                  Up 41 minutes
5904a7c7b41e         cassandra2          7000-7001/tcp, 7199/tcp, 9042/tcp, 9160/tcp                  Up 32 minutes
```

### Check Cluster status
```console
  $docker exec cassandra0 nodetool status
```

### Nodes tool output
```console
Datacenter: datacenter1
=======================
Status=Up/Down
|/ State=Normal/Leaving/Joining/Moving
--  Address     Load       Tokens       Owns (effective)  Host ID                               Rack
UN  172.18.0.2  108.61 KiB  256          64.4%             64652805-6a2e-4144-86d7-86c34ff3aaa9  rack1
UN  172.18.0.3  109.22 KiB  256          67.2%             ac83c203-9883-4058-ba98-cfcccec333c8  rack1
UN  172.18.0.4  88.89 KiB  256          68.5%             5bd39495-7f11-48f9-bb82-3cb319828026  rack1

```