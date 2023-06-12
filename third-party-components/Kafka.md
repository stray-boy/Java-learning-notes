# kafka简介
```
Kafka是一种分布式流处理平台，最初由LinkedIn公司开发，现已成为Apache软件基金会的一部分。Kafka被设计为高吞吐量，低延迟，可扩展，容错的平台，用于处理实时数据流和离线数据流。它具有持久性、可靠性和可伸缩性，适用于构建实时流数据管道和可靠的数据传输系统。Kafka的核心概念包括生产者、消费者和代理（broker），并提供了丰富的API和工具集，使得Kafka易于使用和集成到现有的应用程序中。Kafka广泛应用于日志收集、事件处理、消息传递、指标收集和流处理等场景。
```
# 注意事项
```
kafka遇到的坑，在v2.12是一个分界线，新老版本命令不一致，在创建toptic的时候会出现不同的命令及报错，本次使用的kafka版本是2.12
```
# 安装过程
```

```
# kafka启动命令
bin/kafka-server-start.sh -daemon config/server.properties
查看当前服务器所有的toptic
bin/kafka-topics.sh --zookeeper IP:2181 --list
# 创建topic
```
bin/kafka-topics.sh --create --topic mykafka --replication-factor 1 --partitions 1 --zookeeper localhost:2181
注：字段说明
--topic 定义 topic 名
--replication-factor 定义副本数
--partitions 定义分区数
```
# 查看数据
```
./bin/kafka-topics.sh --zookeeper 192.168.5.104:2181 --list mykafka
```
# 查看toptic信息
```
./bin/kafka-topics.sh --describe --zookeeper localhost:2181 --topic mykafka
```
# 查看toptic从开始接收的消息
```
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic myTopic --from-beginning
```
# 删除topic
```
bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic mykafka
```
# 向topic发送消息
```
bin/kafka-console-producer.sh --brokerlist IP:9092 --topic first
```

# 面试题
1、对Kafka的核心概念有哪些了解？如生产者、消费者、代理等。可以分别介绍一下它们的作用和原理吗？
```
好的，让我来介绍一下Kafka的核心概念：

1. 生产者（Producer）：负责生产消息并将其发送到Kafka集群。生产者将消息发送到指定主题（Topic）的指定分区（Partition）。

2. 消费者（Consumer）：消费者从Kafka集群订阅并消费主题中的消息。消费者可以以不同的方式订阅主题，如按消息顺序、按时间、按键值等。

3. 代理（Broker）：即Kafka集群中的服务器节点。代理负责存储和管理主题的消息，以及处理生产者和消费者的请求。每个代理都是一个独立的进程，可以运行在单独的机器上或者在同一台机器上的不同端口上。

除此之外，Kafka还有其他一些重要的概念，如主题（Topic）、分区（Partition）、偏移量（Offset）和消费者组（Consumer Group）等。这些概念都是Kafka提供的核心机制，对于理解和使用Kafka非常重要。
```
2、您在之前的工作中使用过Kafka吗？如果使用过，能否介绍一下您使用Kafka的场景和具体实现？
```
Kafka被广泛应用于大数据场景中的消息队列、日志收集和分析等方面。以下是一些常见的场景和实现方式：

1. 消息队列：Kafka可以作为一种高性能、高吞吐量的消息队列，用于在分布式系统中传递和处理大量消息。与传统的消息队列相比，Kafka具有更高的可靠性和可扩展性。

2. 日志收集：Kafka可以用于收集和分析日志数据，如应用程序日志、系统日志等。通过将日志数据写入Kafka，可以实现高效的日志收集和处理，并支持实时分析和查询。

3. 流处理：Kafka可以与流处理框架（如Apache Flink、Spark Streaming等）结合使用，用于实现实时数据处理和分析。通过将数据写入Kafka，可以将其转换为流数据，并使用流处理框架进行实时处理和分析。

具体实现方式取决于具体的场景和需求，可以使用Kafka提供的Java、Scala等客户端API进行开发，或者使用Kafka Connect等工具进行配置和部署。同时，还可以使用Kafka的生态系统中的其他组件和工具，如ZooKeeper、Kafka Manager等，来简化和增强Kafka的功能。
```
3、您对于Kafka的消息保证有哪些了解？Kafka提供了哪些消息保证机制？请分别介绍一下它们的作用和使用场景。
```
好的，让我来介绍一下Kafka的消息保证机制：

1. At most once：最多一次，即生产者发送的消息有可能会丢失，但不会重复发送。这种消息保证机制对于一些对消息准确性要求不高，但对消息时效性要求较高的场景适用。

2. At least once：至少一次，即生产者发送的消息必须被消费者至少消费一次，但有可能会重复消费。这种消息保证机制对于一些对消息准确性要求较高，但对消息时效性要求不高的场景适用。

3. Exactly once：恰好一次，即生产者发送的消息必须且只能被消费者消费一次。这种消息保证机制对于一些对消息准确性要求较高，但对消息时效性要求也很高的场景适用。

Kafka提供了多种消息保证机制的实现方式，如单播（Unicast）、多播（Multicast）和广播（Broadcast）等。其中，单播和多播适用于At least once和At most once这两种消息保证机制，而广播适用于Exactly once这种消息保证机制。此外，Kafka还提供了事务（Transaction）机制，用于确保在生产者和消费者之间的消息传输过程中可以保证Exactly once的消息传输。
```
