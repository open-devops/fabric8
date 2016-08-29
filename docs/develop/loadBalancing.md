## 负载均衡

当你有一个或多个 Pods 实现了一个[服务](../services.html)时，你需要在它们中间负载均衡请求。

当你的微服务运行在 Kubernetes 中时，[服务发现](serviceDiscovery.html) 会自动为你在可用的 Pods 中进行负载均衡。

但是当你的微服务被打算向 Kubenretes 集群之外的用户或微服务暴露一个网络应用程序或者 API时，你需要向一个外部主机端口暴露你的微服务。

为了暴露你的微服务，你需要在 Kubernetes 中创建一个 `Ingress（虚拟入口）`资源，它会为你实现外部负载均衡。
 