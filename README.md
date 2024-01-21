# dockerize-kafka

This repository provides a Docker Compose setup for running Apache Kafka along with options to control topics, brokers, and consumers.

## Getting Started

1. Clone the repository:

```
   git clone https://github.com/islamsamy214/kafka-docker-compose.git
   cd kafka-docker-compose/compose-for-localhost
```

2. Start the Kafka containers:

```
docker-compose up -d
```
This will start Kafka

# Controlling Topics

## Create Topics

To create topics, modify the KAFKA_CREATE_TOPICS environment variable in the docker-compose.yml file:

```
environment:
  - KAFKA_CREATE_TOPICS=my-topic:1:1,another-topic:1:1
```

Restart the containers:

```
docker-compose down
docker-compose up -d
```

## List Topics

To list topics, run the following command inside the Kafka container:

```
docker exec -it kafka-container /opt/bitnami/kafka/bin/kafka-topics.sh --list --bootstrap-server localhost:9092
```

Replace kafka-container with the actual name of your Kafka container.
# Controlling Brokers

## Adjust Broker Configuration

To adjust broker configuration, modify the docker-compose.yml file:


```
environment:
  - KAFKA_CFG_<CONFIG_NAME>=<CONFIG_VALUE>
```

For example, to change the broker ID:


```
environment:
  - KAFKA_CFG_BROKER_ID=1
```

Restart the containers.


# Controlling Consumers

## Create Consumers

To create consumers, modify the consumer configuration in your application code or configuration files.


## View Consumer Groups

To view consumer groups, run the following command inside the Kafka container:


```
docker exec -it kafka-container /opt/bitnami/kafka/bin/kafka-consumer-groups.sh --list --bootstrap-server localhost:9092
```

Replace kafka-container with the actual name of your Kafka container.

# Additional Options
## Security (SSL/TLS)

For securing Kafka with SSL/TLS, provide SSL configuration in the docker-compose.yml file and adjust Kafka broker and consumer configurations accordingly.

## Advanced Configuration

For advanced configurations, refer to the official Kafka documentation and customize the docker-compose.yml file accordingly.
<a href="https://hub.docker.com/r/bitnami/kafka">Kafka Bitnami Official Docs</a>

## Cleanup

To stop and remove the containers:

```
docker-compose down
```

This will stop and remove the Kafka and Zookeeper containers.
