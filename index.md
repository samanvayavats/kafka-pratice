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