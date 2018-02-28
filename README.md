# Example set up of flowofcontrol/docker-kafka
This repository only serves as an example setup with docker compose of the flowofcontrol/docker-kafka image.

## Prerequisites
* docker
* docker-compose

## How to run
To run the example simply type:
```
> docker-compose up -d && docker-compose logs -f
```

## Adding it to your docker-compose file
To include the flowofcontrol/docker-kafka and flowofcontrol/docker-zookeeper in their standard setups to your docker-compose.yml file you can simply add:
```
  zookeeper:
    image: flowofcontrol/docker-zookeeper
  kafka:
    image: flowofcontrol/docker-kafka
    depends_on:
      - zookeeper
    links:
      - zookeeper:zookeeper
```
