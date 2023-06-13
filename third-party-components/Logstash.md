# Logstash简介
```
Logstash是一个开源的数据收集引擎，它可以从多个来源（包括日志文件、数据库、消息队列等）收集、处理和转换数据，并将其发送到目标位置（如Elasticsearch、Kafka等）。Logstash提供了一个灵活的管道架构，可以轻松地扩展和自定义数据的处理流程。
Logstash的主要功能包括：
- 输入插件：支持多种数据源的输入，如文件、网络数据流、JMS等；
- 过滤器插件：可对数据进行过滤、解析、转换等处理，如Grok、JSON等；
- 输出插件：支持多种输出方式，如Elasticsearch、Redis、Kafka等。
Logstash可以作为Elastic Stack（ELK）中的一部分，与Elasticsearch、Kibana等组件配合使用，实现实时日志分析和监控。同时，Logstash还支持多种插件，可以轻松地扩展其功能和适应不同的数据源。它具有良好的可扩展性和高可用性，而且支持多种操作系统。
Logstash是一款功能强大的数据收集引擎，适用于日志收集、数据处理和分析等多个场景，帮助用户快速、高效地处理海量数据。
```
# Logstash搭建过程
```
1、安装包地址
https://www.elastic.co/cn/downloads/logstash
2、注意事项
需要注意的是logstash需要和Elasticsearch安装版本号一致，前台展示需要使用kinabna，需要与Elasticsearch版本一致。避免不必要的bug
3、解压logstash
tar -zxvf logstash-7.8.0.tar.gz
4、复制配置文件
cp logstash-sample.conf logstash.conf
5、修改配置文件
input {
  kafka {
    bootstrap_servers => "192.168.5.104:9092"
    topics => ["logToptic"]
  }
}
filter {
  # 使用JSON过滤器将字符串解析为JSON对象
  json {
    source => "message"
    target => "parsed"
  }
}

output {
  elasticsearch {
    hosts => ["http://localhost:9200"]
    index => "logtoptic-%{+YYYY.MM.dd}"
    script => 'ctx._source.remove("expired_at");if (!ctx._source.containsKey("created_at")) {ctx._source.created_at = Instant.now().toEpochMilli();}if(ctx._source.created_at < Instant.now().minus(30, ChronoUnit.DAYS).toEpochMilli()){ctx._source.expired_at = Instant.now().toEpochMilli();}'
    #user => "elastic"
    #password => "changeme"
    # 将解析后的JSON对象写入到Elasticsearch中
    #document => "%{parsed}"
  }
}
6、后台运行程序
bin/logstash -f config/logstash.conf
```

# 面试
```

```
# 心得
```

```

# 优秀项目
```
欢迎推荐
```