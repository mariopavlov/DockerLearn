# 1 Overview
This repo is a docker-compose repo for elasticsearch logstash kibana cerebro


# 2 Instruction
## 2.1 Install Docker
https://docs.docker.com/engine/installation/

## 2.2 Make sure you are under the root directory of the elkc git repo
```
cd elkc
```

## 2.3 Start the elkc cluster
```
docker-compose up -d
```

## 2.4 Stop the elkc cluster
```
docker-compose stop
```

# 3 IMPORTANT NOTE
the cluster spins up 4 docker containers with the name elasticsearch, logstash, kibana and cerebro.
```bash
| => docker ps
CONTAINER ID        IMAGE                   COMMAND                  CREATED             STATUS              PORTS                    NAMES
44c035cf55bc        yannart/cerebro:0.5.0   "./bin/cerebro"          20 minutes ago      Up 14 minutes       0.0.0.0:9000->9000/tcp   cerebro
fac6367ae341        logstash:5              "/docker-entrypoint.s"   8 weeks ago         Up 14 minutes                                logstash
b217e2859ff4        kibana:5                "/docker-entrypoint.s"   8 weeks ago         Up 14 minutes       0.0.0.0:5601->5601/tcp   kibana
05df6bec929d        elasticsearch:5         "/docker-entrypoint.s"   8 weeks ago         Up 14 minutes       9200/tcp, 9300/tcp       elasticsearch
```

If you have existing docker containers that conflict with anyone of the listed name, you have to modify the repo locally a bit to avoid the name conflict, alternatively remove your existing docker container (that had the name conflict)
