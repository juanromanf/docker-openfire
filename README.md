# Dockerized Openfire Server

This docker setup contains a stack with:
* openfire v4.2.3
* mysql v5.7
* adminer

## Requirements
* Docker
* Shell / Console (Git command line)


## Quickstart
Start Openfire using:

```bash
$ docker-compose up
```

## Services
* Openfire Admin Console > http://localhost:9090 
* MySQL Adminer > http://localhost:8080 
* MySQL Server > localhost:3306

## Destroy Stack
```bash
$ docker-compose stop
$ docker-compose rm
$ docker system prune --force --volumes
```