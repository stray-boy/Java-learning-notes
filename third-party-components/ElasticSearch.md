# Elasticsearch简介
```
Elasticsearch是一个基于Lucene的开源搜索引擎，它提供了分布式、多租户、全文搜索、实时分析等功能。Elasticsearch的核心功能在搜索和分析日志、文档和大型数据集上非常有效。

Elasticsearch可以用于存储、搜索和分析各种类型的数据，包括文本、数字、地理位置信息、结构化和非结构化数据等。Elasticsearch的分布式架构使得它可以在多台服务器上同时运行，提供高可用性和可伸缩性。

Elasticsearch的特点包括：

1. 分布式搜索：Elasticsearch使用分布式架构，可以将索引和查询分散到多个节点上，从而加速搜索和查询的速度。

2. 全文搜索：Elasticsearch支持全文搜索，可以在文档中搜索任意字符串，并返回相关的结果。

3. 实时分析：Elasticsearch可以实时分析数据，提供实时的可视化分析结果。

4. 多租户：Elasticsearch支持多租户模式，可以将数据隔离在不同的租户之间，以保护数据的安全。

5. 可扩展性：Elasticsearch使用分片和副本机制来保证数据的可扩展性和高可用性。

Elasticsearch的应用场景包括：

1. 搜索引擎：Elasticsearch可以用于构建企业级搜索引擎，帮助用户快速找到所需的信息。

2. 日志处理：Elasticsearch可以用于存储和分析大量的日志数据。

3. 实时分析：Elasticsearch可以用于实时分析数据，提供实时的可视化分析结果。

4. 安全分析：Elasticsearch可以用于安全分析，帮助企业发现和防范安全威胁。

总之，Elasticsearch是一个强大的搜索引擎，可以用于各种类型的数据存储、搜索和分析。它的可扩展性、高可用性和实时性等特点使得它成为了许多企业数据处理和分析的首选工具。
```
# Elasticsearch安装
```
1、下载文件并解压
tar -zxvf elasticsearch-6.8.1.tar.gz
2、移动文件
mv elasticsearch-6.8.1 ../module/
3、安装的过程中不能够使用root，需要创建角色，本次安装是为零elk架构的搭建，因此创建elk用户组以及elk用户
4、添加用户组
groupadd elk
5、添加用户及密码
useradd elk -g elk -p elk
6、使用root权限给用户赋权
chown -R elk:elk elasticsearch-6.8.1
chown -R elk:elk kibana-6.8.1
7、在安装elasticsearch之前需要修改配置文件，单机只需要修改这些内容即可
# ---------------------------------- Cluster -----------------------------------
# Use a descriptive name for your cluster:
cluster.name: xj-log-5g
# ------------------------------------ Node ------------------------------------
# Use a descriptive name for the node:
node.name: xj-log-5g-node1
# ----------------------------------- Paths ------------------------------------
# Path to directory where to store the data (separate multiple locations by comma):
path.data: /opt/module/elasticsearch-6.8.1/data
# Path to log files:
path.logs: /opt/module/elasticsearch-6.8.1/logs
# ---------------------------------- Network -----------------------------------
# Set the bind address to a specific IP (IPv4 or IPv6):
network.host: 128.129.30.25
# Set a custom port for HTTP:
http.port: 9200
-------------------------------------------------------
path.data: /opt/module/elasticsearch-6.8.1/data
path.logs: /opt/module/elasticsearch-6.8.1/logs
network.host: 192.168.5.104
http.port: 9200
cluster.name: my-application
8、修改完之后进入到elk用户启动会报错内存不足，进入到root用户进行以下操作
9、修改文件句柄
sudo vi /etc/security/limits.conf
* soft nofile 65535
* hard nofile 65535
# 使上面的设置生效
ulimit -n 65535
10、修改进程的最大内存映射区域数量
sudo vi /etc/sysctl.conf
vm.max_map_count=262144
# 使上面的设置生效
sudo sysctl -p
11、然后再进入到用户elk启动就可以了
12、后台启动
nohup bin/elasticsearch  
13、启动后打开出现节点信息
http://192.168.5.104:9200
14、启动密码、设置配置文件
xpack.security.enabled: true
xpack.security.transport.ssl.enabled: true
15、重启程序之后设置密码
bin/elasticsearch-setup-passwords interactive
```
# 面试
```

```

# 个人心得
```

```

# 优秀项目
```
欢迎分享
```
