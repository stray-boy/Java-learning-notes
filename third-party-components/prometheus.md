# prometheus简介



# 后台启动
nohup ./prometheus --config.file=prometheus.yml --web.enable-lifecycle > ./log/prometheus.log 2>&1 &
# 查看启动进程
ps -ef | grep prometheus
前台访问：http://localhost:9090/graph

# 后台启动grafana
./bin/grafana-server web >> log/grafana.log &
账号：admin
密码：grafana
看版模板：https://grafana.com/grafana/dashboards/?search=nginx
前台访问：http://localhost:3000/?orgId=1

# node_exporter 探针（每台客户端上都需要启动，可以监测指标）
nohup ./node_exporter >> log/node_explorter.log &

初始参考文档：https://juejin.cn/post/6948241754030080037