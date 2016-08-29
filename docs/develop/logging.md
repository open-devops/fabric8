## 日志

日志是了解微服务运行状况及诊断问题的重要组成部分。整合日志输出和事件并能够查询和可视化日志是非常有用的工具。

当运行 Fabric8 微服务平台时，我们推荐运行[日志微服务](../logging.html)，它使用 [Elasticsearch](http://www.elasticsearch.com/products/elasticsearch/) 作为后端存储，[Kibana](http://www.elasticsearch.com/products/kibana/) 作为前端展现以及 fluentd 作为日志收集器。

作为一个微服务开发者，你可以使用[日志微服务](../logging.html)免费获得*日志即服务*，但建议你：

* 将日志写到标准输出而非磁盘文件
* 理想状况下使用 JSON 输出以便容易地自动解析