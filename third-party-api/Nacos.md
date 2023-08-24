# Nacos简介
```
Nacos（全称为"Naming and Configuration Service"）是一个开源的分布式服务发现和配置管理系统，由阿里巴巴集团开发和维护。它提供了服务注册与发现、动态配置管理以及服务健康监测等功能，用于帮助构建微服务架构中的基础设施。
作为一个服务注册与发现系统，Nacos可以让不同的微服务实例自动地向其注册，并能够根据需要进行查询和使用这些实例。通过使用Nacos，开发人员可以轻松地对微服务进行扩展、剔除故障节点等操作。
Nacos还提供了动态配置管理功能。它允许将应用程序的配置信息存储在云端，并且支持实时更新这些配置信息。这样一来，在运行期间修改应用程序的配置就变得非常简单和方便。
Nacos还包括一系列其他功能，如灰度发布、流量控制、负载均衡等。它具有良好的可伸缩性和高可用性，并且易于集成到各种平台和框架中。
Nacos是一个功能强大、易于使用且广泛适用于微服务架构中的核心组件。无论你是正在构建新项目还是迁移旧项目到微服务架构中，Nacos都是一个不错的选择。
```
# 注意事项
```
注意对应的版本信息适配信息
```
# 安装过程
```
Windows下安装：
下载：https://github.com/alibaba/nacos/releases/download/2.1.1/nacos-server-2.1.1.zip
解压
修改配置文件

# 配置mysql数据库
### Count of DB:
db.num=1

### Connect URL of DB:  测试环境数据库
db.url.0=jdbc:mysql://10.31.2.2:23306/nacos?characterEncoding=utf8&connectTimeout=1000&socketTimeout=3000&autoReconnect=true&useUnicode=true&useSSL=false&serverTimezone=UTC
db.user.0=root
db.password.0=Maywide_123

### Connection pool configuration: hikariCP
db.pool.config.connectionTimeout=30000
db.pool.config.validationTimeout=10000
db.pool.config.maximumPoolSize=20
db.pool.config.minimumIdle=2

开启鉴权
### If turn on auth system:
nacos.core.auth.system.type=nacos
nacos.core.auth.enabled=true

数据库执行SQL文件


Linux下安装
下载：https://github.com/alibaba/nacos/releases/download/2.1.1/nacos-server-2.1.1.tar.gz
解压
修改配置文件


```
# Nacos启动命令
```
Windows下启动：
单机启动：startup.cmd -m standalone
集群启动：startup.cmd

Linux下启动：



```
# 访问地址
```
访问地址：http://localhost:8848/nacos


```
整合到Spring


# 面试题

```

```

# 个人心得
```
Nacos配置简单，可视化界面易于使用，有完整的生态，充足的文档，学习成本低，应用效率高。
```

# 优秀项目展示
```
欢迎共同补充
```