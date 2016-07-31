## Overview

<b>fabric8</b> 是一个基于 <a href="http://docker.com/">Docker</a>, <a href="http://kubernetes.io/">Kubernetes</a> 和 <a href="https://jenkins.io/">Jenkins</a> 的有态度的开源[微服务平台](fabric8DevOps.html)。

<b>fabric8</b> 通过提供 <a href="http://fabric8.io/guide/cdelivery.html">持续交付流水线</a>， 以及支持持续改善和 <a href="http://fabric8.io/guide/chat.html">聊天运维</a> 的<a href="http://fabric8.io/guide/fabric8DevOps.html">开发运维一体化能力</a> ，使得微服务的创建，构建，测试和部署更加容易。

[Fabric8 微服务平台](fabric8DevOps.html)提供:

* [开发者控制台](console.html)是一个富网络应用程序，他为创建，编辑，构建，部署和测试微服务提供了单一视图
* [持续集成和持续交付](http://fabric8.io/guide/cdelivery.html)通过使用了支持 [Jenkins Workflow Library](jenkinsWorkflowLibrary.html) 的 [Jenkins](https://jenkins.io/)，提供可复用持续交付流水线来帮助你更快及更加可靠地交付软件 
* 通过中央化[日志](http://fabric8.io/guide/logging.html)和[指标矩阵](http://fabric8.io/guide/metrics.html)，[聊天运维](http://fabric8.io/guide/chat.html)和 [Chaos Monkey](http://fabric8.io/guide/chaosMonkey.html)，以及使用 [Hawtio](http://hawt.io/) 和 [Jolokia](http://jolokia.org/) 深度管理 Java 容器来[管理](http://fabric8.io/guide/management.html) 你的应用程序

* 将*集成平台即服务*与你的
[Apache Camel](http://camel.apache.org/) 集成服务的[深度可视化](http://fabric8.io/guide/console.html)[整合](ipaas.html)在一起，提供的 [API Registry](http://fabric8.io/guide/apiRegistry.html) 可以浏览所有的 RESTful 和 SOAP APIs，以及 
[Fabric8 MQ](http://fabric8.io/guide/fabric8MQ.html)  基于 [Apache ActiveMQ](http://activemq.apache.org/)
 提供*消息即服务*

* 提供了 [Java 工具](http://fabric8.io/guide/tools.html)帮助 Java 社区充分利用 [Kubernetes](http://kubernetes.io/):
    * 与 [Kubernetes](http://kubernetes.io/) 一起工作的 [Maven 插件](http://fabric8.io/guide/mavenPlugin.html)
    * 在 [JUnit](http://junit.org/) 中使用 [Arquillian](http://arquillian.org/) 进行 [Kubernetes](http://kubernetes.io/) 资源的
    [结合与系统测试](http://fabric8.io/guide/testing.html)
      
    * [Java ，类库](http://fabric8.io/guide/javaLibraries.html)和支持 [CDI](http://fabric8.io/guide/cdi.html) 扩展 
    
    支持扩展 [CDI](http://fabric8.io/guide/cdi.html)   来和 [Kubernetes](http://kubernetes.io/) 一起工作。

### 平台支持

Fabric8 能很好地与 [Docker](http://www.docker.com/) 和 [Kubernetes](http://kubernetes.io/) 实现一起工作，比如
[Kubernetes 自身](http://kubernetes.io/)，
[OpenShift V3](http://openshift.github.io/)，
[Project Atomic](http://www.projectatomic.io/) 以及
[Google Container Engine](https://cloud.google.com/container-engine/)。

Kubernetes 被广泛支持于 Google 和 Microsofts 云平台， OpenShift
V3（本地部署及公有云）, Project Atomic 及 VMware; 所以 Kubernetes 逐渐成为面向 PaaS 和开放融合云上的 _容器即服务_ 的标准应用编程接口。 