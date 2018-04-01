### Prerequisite
* Docker
* SQL Operations Studio (optional) [more info here](https://github.com/Microsoft/sqlopsstudio)

### Run MSSQL Server container
```console
    docker-compose -f docker-compose.yml up -d
```

### Verify the containers are up and running 
```console
 $ docker ps --format "table {{.ID}}\t {{.Names}}\t {{.Ports}}\t {{.Status}}"
```

### Output
```console
CONTAINER ID         NAMES               PORTS                     STATUS
9ef9c1a2d40e         sqlserver           0.0.0.0:1401->1433/tcp    Up 28 seconds
```

### SQLOpt Studio setup
* Server Name : *localhost,1401*
* User Name : *sa*
* Password : *< refer env file >*

