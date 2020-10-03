# influxdb
influxdb for Kooplex

The image is pulled from `https://hub.docker.com/_/influxdb/`

## Exposed Ports

The following ports are important and are used by InfluxDB.

*    8086 HTTP API port
*   2003 Graphite support, if it is enabled

The HTTP API port will be automatically exposed when using docker run -P.

Find more about API Endpoints & Ports here.

## HTTP API

Creating a DB named mydb:
```
$ curl -G http://localhost:8086/query --data-urlencode "q=CREATE DATABASE mydb"
```
Inserting into the DB:
```
$ curl -i -XPOST 'http://localhost:8086/write?db=mydb' --data-binary 'cpu_load_short,host=server01,region=us-west value=0.64 1434055562000000000'
```
Read more about this in the official documentation
