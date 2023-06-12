# kafka简介
```
Kafka是一种分布式流处理平台，最初由LinkedIn公司开发，现已成为Apache软件基金会的一部分。Kafka被设计为高吞吐量，低延迟，可扩展，容错的平台，用于处理实时数据流和离线数据流。它具有持久性、可靠性和可伸缩性，适用于构建实时流数据管道和可靠的数据传输系统。Kafka的核心概念包括生产者、消费者和代理（broker），并提供了丰富的API和工具集，使得Kafka易于使用和集成到现有的应用程序中。Kafka广泛应用于日志收集、事件处理、消息传递、指标收集和流处理等场景。
```
kafka遇到的坑，在v2.12是一个分界线，新老版本命令不一致，在创建toptic的时候会出现不同的命令及报错，本次使用的kafka版本是2.12

# kafka启动命令
bin/kafka-server-start.sh -daemon config/server.properties
查看当前服务器所有的toptic
bin/kafka-topics.sh --zookeeper IP:2181 --list
创建topic
bin/kafka-topics.sh --create --topic mykafka --replication-factor 1 --partitions 1 --zookeeper localhost:2181
注：字段说明

--topic 定义 topic 名

--replication-factor 定义副本数

--partitions 定义分区数

查看数据
./bin/kafka-topics.sh --zookeeper 192.168.5.104:2181 --list mykafka
查看toptic信息
./bin/kafka-topics.sh --describe --zookeeper localhost:2181 --topic mykafka
查看toptic从开始接收的消息
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic myTopic --from-beginning
删除topic
bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic mykafka
向topic发送消息
bin/kafka-console-producer.sh --brokerlist IP:9092 --topic first