# HOWTO

## Generate initdb.sql by pulling and execute initdb.sh from the image first
* docker pull guacamole/guacamole:latest
* docker run --rm guacamole/guacamole:latest /opt/guacamole/bin/initdb.sh --postgresql > initdb.sql

## Create data folder for PostgreSQL data bind mount
* You can use docker volume if you want
* mkdir -p ./data/pgdata && chown -R 70:70 ./data/pgdata
* PostgreSQL alpine image uses uid/gid 70 (non-alpine image should be 999)
* PostgreSQL should automatically run initdb during the first startup

## Startup
* docker compose up -d
* You should be able to access Guacamole with port 8080
