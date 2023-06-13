# Kibana简介
```
Kibana是一个免费的和开源的数据可视化工具，它是Elastic Stack（之前称为ELK Stack）中的一个组件。Kibana可以与Elasticsearch一起使用，用于分析、搜索和可视化存储在Elasticsearch索引中的数据。

Kibana提供了一个基于Web的用户界面，使用户能够轻松地创建和分享动态仪表板、图表和报表，而无需编写任何代码。通过Kibana，用户可以：

- 监控实时数据：用户可以使用Kibana来监控实时数据，并创建仪表板以查看实时数据的趋势和变化。

- 分析数据：用户可以使用Kibana来分析存储在Elasticsearch索引中的数据，并创建可视化报表和图表以帮助他们理解数据。

- 处理数据：用户可以使用Kibana来处理和转换数据，以便更好地理解和分析数据。

- 可视化数据：用户可以使用Kibana来创建各种类型的可视化图表和报表，以帮助他们更好地理解和分析数据。

Kibana的主要功能包括搜索、过滤、数据可视化、仪表板创建和报告生成。Kibana可以与Elasticsearch一起使用，以便用户能够轻松地分析和可视化存储在Elasticsearch索引中的数据。
```

# 下载文件并安装
```
注意⚠️：需要与ES的版本号保持一致
1、解压文件
tar -zxvf kibana-6.8.1-linux-x86_64.tar.gz
2、移动文件啊
mv kibana-6.8.1-linux-x86_64 ../module/
3、修改文件名
mv kibana-6.8.1-linux-x86_64/ kibana-6.8.1
4、给Kibana加权限
chown -R elk:elk kibana-6.8.1
5、修改配置文件啊

6、启动


7、查看端口号
sudo ss -nlp | grep :5601


```