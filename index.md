# Kafka Practice

Generate a random UUID:

```bat
.\bin\windows\kafka-storage.bat random-uuid
```

Remove the KRaft log directory:

```bat
rmdir /s /q C:\kafka_2.13-4.3.1\kraft-logs
```

Format Kafka storage:

```bat
.\bin\windows\kafka-storage.bat format --standalone -t <random-uuid> -c .\config\server.properties
```

Start the kafka server:

```bat
.\bin\windows\kafka-server-start.bat .\config\server.properties
```

Create the topic:

```bat
.\bin\windows\kafka-topics.bat --create --bootstrap-server localhost:9092 --topic my-group-topic --partitions 3 --replication-factor 1
```

Verify the topic:

```bat
.\bin\windows\kafka-topics.bat --describe --bootstrap-server localhost:9092 --topic my-group-topic
```

List all available Apache Kafka topics:

```bat
.\bin\windows\kafka-topics.bat --list --bootstrap-server localhost:9092
```

Creating the consumer for the comsumer group:

```bat
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic my-group-topic --group my-first-group
```

Producer:

```bat
.\bin\windows\kafka-console-producer.bat --bootstrap-server localhost:9092 --topic my-group-topic
```

Producer with key:

```bat
.\bin\windows\kafka-console-producer.bat --bootstrap-server localhost:9092 --topic my-group-topic --property "parse.key=true" --property "key.separator=:"
```