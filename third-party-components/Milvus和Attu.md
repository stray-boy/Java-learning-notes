# Milvus简介
```
Milvus是一款开源的向量数据库引擎，旨在支持大规模向量数据的存储、检索和分析。它专为高维度向量数据而设计，并具有良好的可扩展性和高效的查询性能。

以下是Milvus主要特点：

1. 高性能：Milvus基于多核CPU并行处理，结合了优化算法和索引技术，提供快速且准确的相似度搜索功能。
2. 多种相似度计算方法：支持欧氏距离、内积等多种相似度计算方法，满足不同应用场景下的需求。
3. 可扩展性：通过水平扩展来支持海量数据集，并且可以动态地添加或删除节点以适应实际需求。
4. 多语言支持：提供Python、Java、Go等各种编程语言的SDK，方便用户进行开发和集成。
5. 灵活部署方式：可以选择本地部署或者云端部署，在私有云或公有云上都可使用。

Milvus作为一个快速、可扩展且功能强大的向量数据库引擎，在很多领域如图像识别、自然语言处理、推荐系统等都得到广泛应用。
```
# 下载Milvus
```
docker安装
注释：milvus-standalone-docker-compose.yml and save it as docker-compose.yml
下载手动：wget https://github.com/milvus-io/milvus/releases/download/v2.0.2/milvus-standalone-docker-compose.yml -O docker-compose.yml
```
# 安装Milvus
```
进入当前文件夹执行命令：
sudo docker-compose up -d

```
# 查看启动状态
```
sudo docker-compose ps
      Name                     Command                  State                          Ports
----------------------------------------------------------------------------------------------------------------
milvus-etcd         etcd -listen-peer-urls=htt ...   Up (healthy)   2379/tcp, 2380/tcp
milvus-minio        /usr/bin/docker-entrypoint ...   Up (healthy)   9000/tcp
milvus-standalone   /tini -- milvus run standalone   Up             0.0.0.0:19530->19530/tcp,:::19530->19530/tcp
停止：
sudo docker-compose down
删除数据
sudo rm -rf  volumes
```
# 个人心得
```
注意Milvus与Attu的版本对应保持一致，都则会连接不上

```
# 面试
```

```
# 优秀项目地址
```
欢迎推荐
```

# Attu简介
```
可以当作是Milvus的连接器
```
# 下载Attu
```

```
# 安装Attu
```
docker run -itd --restart=always -p 13000:3000 -e HOST_URL=http://localhost:13000 -e MILVUS_URL=127.0.0.1:19530 zilliz/attu:v2.0.5
```
# 查看启动状态
```
docker ps
```
# 个人心得
```
使用IP连接：192.168.3.17:19530
与Milvus版本对应，否则会连接不上
```
# 面试
```

```
# 优秀项目地址
```
欢迎推荐
```
