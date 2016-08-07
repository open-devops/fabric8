### 一般性问题

#### 许可证采用了那种？

fabric8 使用 [Apache 2.0 许可证](http://www.apache.org/licenses/LICENSE-2.0.txt)。

#### 什么是 Fabric8？

Fabric8 是个集成开源的 [DevOps](fabric8DevOps.html) 和 [集成平台](ipaas.html)，它可以直接工作在任何 [Kubernetes](http://kubernetes.io/) 或 [OpenShift](http://www.openshift.org/) 环境中，它提供了[持续交付](cdelivery.html), [管理门户](management.html)，[聊天运维](chat.html) 以及 [Chaos Monkey](chaosMonkey.html).

#### Fabric8 能做什么？

Fabric8 （发音为 _fabricate_） 给你开箱即用的服务来辅助你构建 Linux 容器（Docker/Rocket）环境中的微服务，单块应用或者任何应用程序，它构建在 [Kubernetes](http://kubernetes.io/) 之上。

#### Fabric8 在 OpenShift 之上提供了什么增值服务？

* [Kubernetes](http://kubernetes.io) 提供了一个基于 [Docker](http://docker.io/) 的 _容器即服务_ （编排 Docker 容器）
* [OpenShift V3](https://github.com/openshift/origin) 扩展了 Kubernetes 来支持完整的*平台即服务*
  * 在 Git 仓库托管源代码
  * 执行构建和托管私有 Docker 镜像
  * 支持 Git Push 方式来启动新的构建
* Fabric8 致力于:
  * 提供令人满意的基于 [hawtio](http://hawt.io/) 的 [Kubernetes 控制台](console.html)， 你可以浏览所有的 kubernetes 资源，理解发生了什么事情。既可以看到整体情况，又可以聚焦进个别容器，提供日志和各项指标的链接。
  * 成为一个**集成平台即服务**和 **Java 应用平台即服务**
  * 增加额外的服务，工具与快速入门来使 Kubernetes 平台为 Java 生态系统提供更丰富和更强大的功能：
    * [Fabric8 应用](fabric8Apps.html) 提供可复用的[日志](logging.html), [指标](metrics.html)，并可以更加容易地使用集成与消息服务
    * 提供深度支持并且功能丰富的[工具](http://fabric8.io/guide/tools.html)来使在 Kubernetes/OpenShift 上开发 Java 应用程序更加容易。比如[Maven Plugin](http://fabric8.io/guide/mavenPlugin.html) 和 [Forge Addons](http://fabric8.io/guide/forge.html)。
    * 提供 [Java 类库](javaLibraries.html) 连同 [kubernetes & jolokia](https://github.com/fabric8io/fabric8/tree/master/components/kubernetes-jolokia) 一起和 [kubernetes](https://github.com/fabric8io/fabric8/tree/master/components/kubernetes-api) 工作，使得开发基于 Java 的与 Kubernetes 融洽工作的工具和服务更加容易
    * [使用 Arquillian 测试](testing.html)帮助你进行[应用](apps.html)的集成测试
    * 通过很多加工使 JBoss 中间件成为可复用构件，以使它们在通用控制台和平台上很容易地被消费

#### Fabric8 是以 Java 为中心的吗？

简短回答为：不是 ;).

* [Fabric8 管理功能](management.html) 能和任何 [Kubernetes](http://kubernetes.io/) 上的 Docker 镜像一起工作  - 所以它是完全与语言，框架和运行时无关的。 [控制台](console.html) 为包含了 [Jolokia](http://jolokia.org/) 的 Java Docker 容器增加了额外的自省和可视化，但是我们希望为其他语言增加更多的深度自省工具。当然你总是可以在 Kubernetes 上直接使用任何语言，框架或者运行时特定的诊断或可视化工具
* [微服务平台](fabric8DevOps.html)致力于与使用任何构建机制在 [Kubernetes](http://kubernetes.io/) 上运行 Docker 镜像的任何项目一起工作，所以支持使用任何构建工具的任何语言，框架和运行时。 不管是使用 OpenShift 的[源代码到镜像构建机制](https://docs.openshift.com/enterprise/3.0/architecture/core_concepts/builds_and_image_streams.html#source-build)，还是使用了 [Jenkins 流水线](https://github.com/jenkinsci/workflow-plugin)的我们首选的[持续交付](cdelivery.html)
* [Fabric8 iPaaS（集成平台）](ipaas.html)的集成流程倾向于使用 [Apache Camel](http://camel.apache.org/) 实现，而它运行在 Java 虚拟机中，从这个角度来说，是更加以 Java 为中心的。但是 [Apache Camel](http://camel.apache.org/) 集成的服务可以使用任何技术，语言，运行时，本地部署或者 SaaS
* [Fabric8 API 管理功能](apiManagement.html)可以与任何语言或运行时实现的 API 一起工作，虽然现在只支持基于 HTTP 的 API

说了所有这些，[Fabric8 iPaaS](ipaas.html) 致力于优化 Fabric8 以使 Java 的用户拥有与 Docker，Kubernetes，OpenShift 及 Fabric8 一起工作的优化体验， 但是我们也希望持续改进工具链，管理门户和可视化为其他语言和运行时服务

#### Jenkins 流水线是以 Java 为中心的吗？

我们[持续交付](cdelivery.html)的首选工具为基于 [Jenkins](https://jenkins.io/) 的 [Jenkins 流水线插件](https://github.com/jenkinsci/workflow-plugin)。

Jenkins 流水线使用 [Groovy 编程语言](http://groovy-lang.org/)为编排长时间运行的构建任务（比如构建，测试，审批，提升与部署等步骤）提供了领域特定语言。 

使用 Jenkins流水线的首选方式是，为你的所有构建和测试工具重用 Docker 镜像，以使**Jenkinsfile**文件的大部分构建细节趋向于 Docker 镜像中的命令运行。因此你的持续交付流水线的定义一般是一个命令列表，命令可以是你使用的任何工具（Maven, Grunt, Gulp, Make, bash, python, ruby 等等），它们是完全地和语言，工具，框架无关的。

#### 微服务平台能够和我的持续集成服务器一起工作吗？

我们[持续交付](cdelivery.html)的首选工具为基于 [Jenkins](https://jenkins.io/) 的 [Jenkins 流水线插件](https://github.com/jenkinsci/workflow-plugin)。

但是这个*编排交付流水线*一般包括很多任务，比如构建，测试，审批，提升与部署。这些组成构件的每一个如何工作是完全取决于你的。
 
 比如你可以重用你的现有持续集成服务器（Jenkins, Bamboo, TeamCity 或者其他）来构建你的代码，然后使用 Jenkins 流水线来在环境间移动构建成果物，编排系统测试，侵泡测试，验收测试，审批，提升及部署等。

当我们试图实现[持续交付，持续部署或者持续改进](cdelivery.html)时，我们的首选方式为使用 Jenkins 流水线作为核心编排层， 然后在这个流水线上触发任何所需处理来完成流水线任务，不管它是现有持续集成服务器的一个或者多个构建任务，还是触发 OpenShift [源代码到镜像构建](https://docs.openshift.com/enterprise/3.0/architecture/core_concepts/builds_and_image_streams.html#source-build)，或者其他现有构建任务或测试服务，然后通过 Jenkins 流水线，与审批和提升一起编排这些处理。这也意味着可以更加容易地获得你的跨越所有项目的持续交付流水线的holistic视图，不仅包括每个构建或测试如何工作，还包括构建或测试项目中使用的工具信息。

#### 我在哪里可以找到源代码？

Fabric8 是由 Java 和 Go 语言开发的并打包成 Docker 容器的项目集合构成。这些项目／容器的 Git 仓库的详细信息可以在[项目文档页面](projects.md)找到。 

#### 运行 Fabric8 需要 Docker 和 Kubernetes吗？

Fabric8 被设计为在 Kubernetes 和 Docker 之上工作最佳，这意味着 Fabric8 会在提供 Kubernetes 平台的任何环境中工作良好，比如 RHEL Atomic, OpenShift, Google Compute Engine, Azure 等等。

#### 支持 Windows 吗？

我们建议在生产环境使用基于 Linux 的操作系统，尤其是你想要使用 [Docker](http://docker.io/) 和 [Kubernetes](http://kubernetes.io) 或 [OpenShift Origin V3](https://github.com/openshift/origin) 的全面管理平台。 

Windows 现在只是部分支持。Windows 用户也许可以考虑使用 [Docker](http://docker.io/)，这样所有 Fabric8 技术棧运行在一个 Linux 虚拟机的轻量级容器中。

#### 提供了哪些 Maven 插件目标？
 
浏览[ Maven 插件目标列表](http://fabric8.io/guide/mavenPlugin.html) 

#### 支持 Java 的那些版本？

Fabric8 的 Java 源代码使用 Java 8，但是 Docker 镜像可以使用它所希望的任何语言，运行时或者框架的任何版本。

#### Fabric8 使用 ZooKeeper 运行时注册服务吗？

不，再也不需要了。 Fabric8 1.x 使用 ZooKeeper 在应用程序之间分享运行时信息并发现服务。Kubernetes 在内部使用 [etcd](https://github.com/coreos/etcd) 达到同样的目的并支持服务绑定，所以 Fabric8 v2 再也不需要 ZooKeeper 注册服务来进行容器和服务的通用配置。

但是一些服务还是会需要主从选举和分区功能（比如运行 ActiveMQ 集群)，这时需要 [etcd](https://github.com/coreos/etcd) 或者 [Apache ZooKeeper](http://zookeeper.apache.org/)。 如果 Kubernetes 环境条件允许，那么 Fabric8 可以重用底层的
  etcd 集群，否则需要 etcd 或者 ZK 集群来为像 ActiveMQ 集群之类的东西服务。

#### Fabric8 还在使用 Profiles 配置应用程序部署吗？

不，再也不需要了。从 Fabric8 V2 开始，Fabric8使用 [应用程序](apps.html) JSON 文件（比如 OpenShift 3 提议的 Kubernetes 扩展）来配置受管应用程序的部署。更详细的配置（比如属性或者 YAML 文件）可以添加到应用程序的 Docker 镜像的文件系统中。

#### 还需要使用 Git 仓库来存储应用程序的配置信息吗？

和 Fabric8 v1 不同，应用程序的配置信息不再被保存在 Git 仓库中。由于 Fabric8 v2 不再使用 Profiles （但是替代地使用应用程序模版），再也不需要 Git 仓库了。你可以只是将应用程序的配置（应用程序文件）保存在 Maven 项目中并使用 [Fabric8 Maven  插件](mavenPlugin.html#running) 来在 Kubernetes 中启动应用程序，而不需要在任何中央仓库（比如 Git）保存配置信息。

但是为了更加容易的配置管理，推荐在 Git 中保存应用程序文件。这也是为什么 Fabric8 为本地部署的 Git 仓库托管默认集成了 [Gogs](http://gogs.io/) 的原因。 这来自于 [Fabric8 DevOps](fabric8DevOps.md) 特性。

#### 是否需要 Fabric8 Server 来配置应用程序？

不，再也不需要了。从 Fabric8 v2 开始，Kubernetes 负责为受管应用程序提供运行时注册服务。这意味着你不再需要启动任何专属的 Fabric8 守护进程。像 
[Fabric8 Maven 插件](mavenPlugin.html)
或者 [Hawt.io](http://hawt.io) 之类的工具可以直接连接 Kubernetes 来部署管理应用程序。

#### 如果不再有 Fabric8 Server，我怎么使用 Fabric8 Shell？

对于 Fabric8 v2 开发活动，推荐工具为 [JBoss Forge](http://forge.jboss.org) 和 [Fabric8 add-on](forge.html)。

为了应用程序服务开通的目的（比如创建容器／服务，或者变更副本数量），你可以使用 [Fabric8 add-on](forge.html) 或者使用 OpenShift/Kubernetes 的 Shell。

Kubernetes 被包含在 [Red Hat Enterprise Linux](http://www.redhat.com/en/technologies/linux-platforms/enterprise-linux) 和 OpenShift V3 之中，是用来配置任何类型容器的标准 Shell。

#### 废弃

FAB (Fuse Application Bundles) 在 1.2 版本中被废弃，从 2.x 版本被移除。