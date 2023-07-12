## Installation

Download from https://kafka.apache.org/downloads 

## Usage

Unzip the downloaded file anywhere on your computer. Scripts can be found in the bin folder. 

### Start/Stop Service

```sh
bin/zookeeper-server-start.sh config/zookeeper.properties
bin/kafka-server-start.sh config/server.properties
```

### Create Topic

```sh
bin/kafka-topics.sh --create --bootstrap-server localhost:8097 --replication-factor 1 --partitions 2 --topic demo
```

### List Topics

```sh
bin/kafka-topics.sh --list --bootstrap-server localhost:8097
```

### Describe Topics

```sh
bin/kafka-topics.sh --bootstrap-server localhost:8097 --describe --topic demo
```

### Delete Topics

```sh
bin/kafka-topics.sh --bootstrap-server localhost:8097 --delete --topic demo
```

### Create Producer

```sh
bin/kafka-console-producer.sh  --bootstrap-server localhost:8097 --topic demo
```

### Create Consumer

```sh
bin/kafka-console-consumer.sh --bootstrap-server localhost:8097 --topic demo --from-beginning --group console
bin/kafka-console-consumer.sh --bootstrap-server localhost:8097 --topic demo --from-beginning --partition 0
bin/kafka-console-consumer.sh --bootstrap-server localhost:8097 --topic demo --partition 0 --offset latest
```