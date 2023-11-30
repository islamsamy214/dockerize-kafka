# dockerize-kafka
A simple kafka docker with its zookeeper
# Kafka and Zookeeper Docker Compose Setup

This repository contains a Docker Compose configuration for running Apache Kafka and Zookeeper in a Docker environment. It allows you to easily set up a Kafka broker for development or testing purposes.

## Prerequisites

Before getting started, make sure you have the following installed on your system:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Usage

1. Clone this repository to your local machine:

    ```bash
    git clone https://github.com/your-username/kafka-zookeeper-docker-compose.git
    ```

2. Change into the cloned directory:

    ```bash
    cd kafka-zookeeper-docker-compose
    ```

3. Edit the `docker-compose.yml` file if needed. You can modify Kafka configurations, add topics, or change container names according to your requirements.

4. Build and start the containers:

    ```bash
    docker-compose up -d
    ```

   This will download the required images and start the Kafka and Zookeeper containers in the background.

5. To stop the containers, run:

    ```bash
    docker-compose down
    ```

## Configuration

### Kafka Configuration

You can customize Kafka settings in the `docker-compose.yml` file under the `kafka` service. Key configuration options include:

- `KAFKA_ADVERTISED_LISTENERS`: Defines the advertised listeners for Kafka.
- `KAFKA_CREATE_TOPICS`: Allows you to specify topics and their configurations.
- ...

### Network Configuration

By default, a bridge network named `microservices-network` is used. You can customize the network settings in the `docker-compose.yml` file under the `networks` section.

## Contributing

Feel free to contribute to this project by opening issues or submitting pull requests. Your feedback is highly appreciated!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Donation

Buy me a coffee: https://www.buymeacoffee.com/islamsamy
