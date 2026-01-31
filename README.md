# aiops-summitlab
This repo will be used for the Summit 2025 AIOps Lab







## Working with containers on the service1 node

We have provided containers that are working on the service1 node.  You can attach to the bash terminal by doing this:

```
podman exec -it cp-kafka bash
```


## Working with Kafka


Here are some basic commands and troubleshooting:


1. List all topics on kafka:

```bash
podman exec cp-kafka /opt/kafka/bin/kafka-topics.sh --list --bootstrap-server localhost:9092
```

2. Creating a topic called `httpd-error-logs`:

```bash
podman exec cp-kafka /opt/kafka/bin/kafka-topics.sh --create --topic httpd-error-logs --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
```

3. Retrieving all logs from the `httpd-error-logs` topic:

```bash
podman exec -it cp-kafka /opt/kafka/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic httpd-error-logs --from-beginning
```

## Working with filebeat

You can test error logs like simply using the echo command like this:

```bash
echo "Test error message $(date)" >> /var/log/httpd/error_log
```