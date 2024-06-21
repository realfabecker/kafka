# Kafka

## Create a Topic

Create a Kafka topic using the following command:

```bash
docker exec -it \
    <kafka-container-id> /opt/kafka/bin/kafka-topics.sh \
    --create \
    --zookeeper zookeeper:2181 \
    --replication-factor 1 \
    --partitions 1 \
    --topic my-topic
```

## Produce Messages

Use the Kafka console producer and consumer to test your Kafka setup:

```bash
docker exec -it \
        <kafka-container-id> /opt/kafka/bin/kafka-console-producer.sh \
        --broker-list localhost:9092 \
        --topic my-topic
```

## Consume messages:

```bash
docker exec -it \
    <kafka-container-id> /opt/kafka/bin/kafka-console-consumer.sh \
    --bootstrap-server localhost:9092 \
    --topic my-topic --from-beginning

```