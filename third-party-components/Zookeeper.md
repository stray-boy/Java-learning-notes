# Zookeeper简介
```
ZooKeeper是一个开源的分布式协调服务，旨在为分布式应用程序提供高性能、高可用性和可靠性的服务。它提供了一个类似于文件系统的层次结构，这个层次结构可以用于存储和管理分布式应用程序中的各种元数据、状态信息和配置数据。

ZooKeeper最初是由雅虎研究员创建的，现在已经成为了一个Apache顶级项目。它采用了基于观察者模式的通知机制，可以在节点状态发生变化时通知客户端应用程序，同时还提供了强一致性、顺序性和持久性等特性，使得分布式应用程序可以更加简单地实现协调和同步。

ZooKeeper主要有三个用途：

1. 提供分布式锁服务，使得分布式应用程序可以通过锁机制实现同步和协调。

2. 维护分布式应用程序的元数据和状态信息，使得分布式应用程序可以共享数据和状态信息。

3. 提供可扩展的服务发现功能，使得分布式应用程序可以自动发现并连接到可用的服务。

ZooKeeper的特点包括：

1. 简单易用：ZooKeeper提供了类似于文件系统的数据结构和API，使得开发人员可以很容易地使用它来实现分布式应用程序。

2. 高性能和高可用性：ZooKeeper使用了类似于Paxos算法的协议来实现强一致性，同时还提供了数据缓存和异步更新等机制来提高性能和可用性。

3. 可扩展性：ZooKeeper可以很容易地通过添加更多的服务器节点来扩展其性能和可用性。

ZooKeeper是一个非常有用的分布式服务，可以帮助开发人员实现更加可靠、高效、可扩展的分布式应用程序。
```
# 下载Zookeeper
```

```
# 安装Zookeeper
```
1、解压
tar -zxvf zookeeper-3.4.10.tar.gz
2、移动文件夹
mv zookeeper-3.4.10 ../module/
3、复制配置文件并修改
cp zoo_sample.cfg zoo.cfg
修改dataDir文件指向：/opt/module/zookeeper-3.4.10/data
4、启动Zookeeper，查看状态status，关闭stop
bin/zkServer.sh start
```
# 查看启动状态
```
JPS  查看正常运行的zookeeper
22540 QuorumPeerMain
```
# 个人心得
```

```
# 面试
```

```
# 优秀项目地址
```
欢迎推荐
```



