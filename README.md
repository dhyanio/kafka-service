# kafka-service
Distributed system with Kafka

- Node.js
- Docker

### Docker Commands
- Run Zookeeper
```text
docker run --name zookeeper  -p 2181:2181 -d zookeeper
```

- Run Kafka
```text
docker run -p 9092:9092 --name kafka  -e KAFKA_ZOOKEEPER_CONNECT=localhost:2181 -e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://localhost:9092 -e KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR=1 -d confluentinc/cp-kafka
```
`KAFKA_ZOOKEEPER_CONNECT`: Zookeeper address

`KAFKA_ADVERTISED_LISTENERS`: Kafka address

`KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR`: By, default kafka create 3 topic replication, so we need to define 1 here.
