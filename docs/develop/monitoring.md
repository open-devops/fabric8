## 监控

捕获历史指标信息对于诊断你的微服务的问题十分必要。它对于[自动缩放](elasticity.html)也非常有用。

所以我们建议运行[Metrics（指标）微服务](../metrics.html)，它使用 [Prometheus](http://prometheus.io/) 作为后端存储服务和 REST API，并使用 [Grafana](http://grafana.org/) 作为控制台来浏览、查询以及分析指标。

如果你使用 Java，那么使用一个 [JMX Exporter YAML 文件](https://github.com/prometheus/jmx_exporter) 可以指定导出哪个 JMX 指标给 Prometheus。