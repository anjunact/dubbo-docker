# Dubbo in Docker Example

Dubbo running in Docker, packaged as a springboot application.

## Services

This demo consistes three services:

- a zookeper instance
- a service producer
- a service consumer

The service producer exposes a ```Greeting``` service through RPC,
service consumer access the producer.

## Zookeeper

Run a docker image.

## Service Producer

Code in [service-producer](service-producer). API defined in [service-api](service-api).

mvn install  // 安装依赖到本地

Build docker image:

```
cd service-producer
mvn package
mvn install

```

## Service Consumer

Code in [service-consumer](service-consumer). 

Build docker image:

```
cd service-consumer
mvn package
mvn install

```

## Run

Use docker-compose command to run it.

```
cd docker
docker-compose up --build
```

Verify that all works:
```
$curl http://localhost:8899/
Greetings from Dubbo Docker
```

## Run it on Alibaba Cloud

Use [docker/docker-compose-acs.yml](docker/docker-compose-acs.yml) to deploy this application to 
Aliyun Container Service (Alibaba Cloud).