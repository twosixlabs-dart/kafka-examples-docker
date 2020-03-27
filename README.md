# Two Six Labs - DART Kafka Application Templates

## Overview
This project contains examples of the three core types of Kafka Applications deployed in DART. Currently, examples are provided in Python, Java, and Scala. If you would like to contribute another example, please open a PR.

## Running the Examples
Each example contains a fully integrated Kafka streaming pipeline. In order to run the examples, you will need to have both [Docker](https://docs.docker.com/install/) and [Docker Compose](https://docs.docker.com/compose/install/) installed.

To run the example use `docker-compose` to run the application sample you are interested in

Copy that file to a local directory, and from that directory run:

```$xslt
# Java
docker-compose -f java.yml pull
docker-compose -f java.yml up -d

# Python
docker-compose -f python.yml pull
docker-compose -f python.yml up -d

# Scala
docker-compose -f scala.yml pull
docker-compose -f scala.yml up -d
```

The applications will log their behavior to std.out, in accordance with Docker conventions.
To see the logs of a container:
```bash
docker logs -f <contained_id>
```

To check the output of the *Consumer*:
```bash
docker exec -it <consumer_container_id> /bin/bash # this will log you into the container's CLI
ls -al /opt/app/data
```

The consumer application should write a random file to `/opt/app/data/` every two seconds.

To stop the process, run:
```$xslt
# Java
docker-compose -f java.yml down

# Python
docker-compose -f python.yml down

# Scala
docker-compose -f scala.yml down
```