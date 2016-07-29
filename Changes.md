
### 2.2.16

* [Fabric8 DevOps](http://fabric8.io/guide/fabric8DevOps.html)拥有新的[基于聊天](http://fabric8.io/guide/chat.html)的[工作流步骤](https://github.com/fabric8io/fabric8-jenkins-workflow-steps)，可以在类似 Lets Chat 或者 Slack 这类聊天应用里进行基于 Jenkins 工作流的[持续部署流水线](http://fabric8.io/guide/cdelivery.html)的通知及审批。这里有一个使用了 [Jenkins 工作流的 Fabric8 DevOps 可重用库](https://github.com/fabric8io/jenkins-workflow-library)的[展示样例](https://github.com/fabric8io/fabric8-jenkins-workflow-steps#hubotapprove)
* 所有的 [Kuberentes 集成测试用例](http://fabric8.io/guide/testing.html)在[Fabric8 DevOps 可重用 Jenkins 工作流](https://github.com/fabric8io/jenkins-workflow-library) 中都会被默认调用
* 修复了[10个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.2.16)

* **注意** 我们强烈建议所有的 fabric8 用户尽快升级到这个发布版本。 这个发布版本修复了[一个问题](https://github.com/fabric8io/fabric8/issues/4520)，这个问题发生在 Chrome 近期版本，由于我们在 OpenShift OAuth 登录期间使用了错误的 URL，导致除非明示地信任证书，否则不能登录到[控制台](http://fabric8.io/guide/console.html)

### 2.2.14

* 这个版本修复了一些在 OpenShift 1.0.2 或之后的版本中发现的，使用 [Fabric8 DevOps 持续部署](http://fabric8.io/guide/cdelivery.html)场景中的功能退步  
* 在[控制台](http://fabric8.io/guide/console.html)中添加了到[持续部署环境变量](http://fabric8.io/guide/cdelivery.html) 更好看的链接
* 修复了[2个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.2.14)

### 2.2.12

* 升级到最新 kubernetes 1.0 结构。这个版本现在可以工作在 OpenShift Origin 1.0.2 或者以后的版本上
* 在使用[ Fabric8 DevOps 持续发布](http://fabric8.io/guide/cdelivery.html)场景中，支持全面可用的金丝雀发布，预发布，审批并推进在 Jenkins 工作流中的构建过程
* 修复了[5个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.2.12)

### 2.2.11

* 在这个发布版本中，[fabric8 控制台](http://fabric8.io/guide/console.html)可以工作在纯粹的[ kubernetes 和 GKE ](http://fabric8.io/guide/getStarted/gke.html)之上，也可以工作在 OpenShift 之上。查看这个[演示视频](https://vimeo.com/133765913) 看它如何工作在 GKE 之上
* [mvn fabric8:apply](http://fabric8.io/guide/mavenFabric8Apply.html) 目标现在可以直接工作在纯粹的 Kubernetes 和 OpenShift 之上，你不需要配置任何属性
* 增加了为了减少键盘输入的 [mvn fabric8:recreate](http://fabric8.io/guide/mavenFabric8Recreate.html) 目标，如果你想确保所有的资源被创建或者重新创建的场景可以使用它
* 修复了[18个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.2.11)

### 2.2.7

* 新的基于 [Jenkins Docker 工作流](http://documentation.cloudbees.com/docs/cje-user-guide/docker-workflow.html)的[持续集成与持续交付系统](http://fabric8.io/guide/cdelivery.html)的首个发布版本
* 提供 [fabric8-devops-connector](https://github.com/fabric8io/fabric8/tree/master/components/fabric8-devops-connector) 内在支持来连接各种不同 DevOps 服务。比如为一个重用了 `fabric8.yml` 可选文件的项目提供 git 托管，聊天，问题跟踪，以及 jenkins等服务，这些服务运行在 JBoss Forge， Maven 或者一个 JVM上
* `fabric8:create-build-config` 目标现在被重命名为 `fabric8:devops` 来体现通过 [fabric8-devops-connector](https://github.com/fabric8io/fabric8/tree/master/components/fabric8-devops-connector) 更新 DevOps 配置的本质  
* 修复了[16个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.2.7)

### 2.2.5

* 增加了新的项目向导，现在你可以像这个[示例](https://github.com/fabric8io/fabric8/blob/master/components/fabric8-devops/src/test/resources/fabric8.yml)一样配置 [fabric8.yml 文件](https://github.com/fabric8io/fabric8/issues/4086)，进行项目的 DevOps 设定，比如聊天室，项目问题追踪系统，是否需要代码评审等方面。当我们迁移到 [Jenkins Docker 工作流](https://github.com/fabric8io/fabric8/issues/4286)进行构建之后，我们也能够使用这个配置好的工作流
* 修复了[13个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.2.5)

### 2.2.3

* 当使用 [vagrant 镜像](http://fabric8.io/guide/getStartedVagrant.html)时，你可以通过按下[控制台](http://fabric8.io/guide/console.html)的 `Apps` 选项卡的 `Run...` 按钮，来直接运行 [Metrics](http://fabric8.io/guide/metrics.html) 和 [Logging](http://fabric8.io/guide/chat.html)    
* [聊天](http://fabric8.io/guide/chat.html)现在可以直接使用，而无需手动配置聊天室和凭证以及将它们传递给命令行以使 Hubot 可以连接到 Let's Chat
* 修复了[3个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.2.3)

### 2.2.2

* 增加了基于新的更易使用的[vagrant 镜像](http://fabric8.io/guide/getStartedVagrant.html)的入门指南 
* vagrant 域名现在为 `vagrant.f8`，在 vagrant 镜像内部为支持 DNS 做好准备
* 你现在可以容易地从[控制台](http://fabric8.io/guide/console.html)的 `Run...` 按钮运行 [fabric8 应用](http://fabric8.io/guide/fabric8Apps.html) 
* 修复了[39个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.2.2)

### 2.2.0

* 更新到 kubernetes schema `v1` 版本 
* [fabric8 vagrant 镜像](http://fabric8.io/guide/openShiftWithFabric8Vagrant.html)被移动到 [fabric8-installer](https://github.com/fabric8io/fabric8-installer/tree/master/vagrant/openshift-latest) 仓库
* 修复了[15个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.2.0)

### 2.1.11

* 修复了[3个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.1.11)

### 2.1.10

* 修复了[8个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.1.10)

### 2.1.6

* 修复了[39个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.1.6)

### 2.1.1 

* 改善了[用户指南](http://fabric8.io/guide/)， 使如何[在 OpenShift V3 上安装 Fabric8](http://fabric8.io/guide/fabric8OnOpenShift.html) 的指令更加明了
* 迁移到默认包含许多更好的验证功能的 v1beta3 版本的 Kubernetes schema 上
* [Fabric8 应用](http://fabric8.io/guide/fabric8Apps.html)现在通过使用 [OpenShift 模板](http://docs.openshift.org/latest/dev_guide/templates.html) JSON 文件，能够更容易被[安装到既有 Kubernetes 或者 OpenShift 环境上](http://fabric8.io/guide/fabric8OnOpenShift.html)
* Maven [fabric8:json](http://fabric8.io/guide/mavenFabric8Json.html) 目标现在支持生成 [OpenShift 模板](http://docs.openshift.org/latest/dev_guide/templates.html)
* Maven [fabric8:apply](http://fabric8.io/guide/mavenFabric8Apply.html) 目标为旧有 `fabric8:run` 目标的新名称，以便更好的描述适用 JSON 到 kubernetes 环境以及创建/更新/删除资源的用途
* 增加了新的 maven [fabric8:create-routes](http://fabric8.io/guide/mavenFabric8CreateRoutes.html) 来延迟创建任何缺失的 [OpenShift 路由](http://docs.openshift.org/latest/admin_guide/router.html)
* 由于 websockets 实时更新的支持，[fabric8 控制台](http://fabric8.io/guide/console.html)更加反应灵敏
* 首个 [Fabric8 持续交付](http://fabric8.io/guide/cdelivery.html)发布使得构建更加容易，发布和配置软件更加快速及可靠
* 修复了[49个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.1.1)

### 2.0.44

* 修复了[5个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.44)

### 2.0.43

* 修复了[2个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.43)

### 2.0.40

* 通过 [hubot](https://hubot.github.com/) 提供[聊天支持](http://fabric8.io/guide/chat.html)，将构建完成或失败信息通知给IRC, Slack, HipChat, Campfire等聊天室
* 修复了[5个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.40)

### 2.0.36

* 修复了[20个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.36)

### 2.0.32

* 修复了[60个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.32)

### 2.0.29

* 迁移到 hawtio 2.x，通过[可选模块化服务](http://fabric8.io/guide/fabric8Apps.html)使得控制台更小更轻量级
* 增加了 [App Library](appLibrary.html) 来提供一个可配置的应用库以使你能容易地运行、安装、卸载应用，类似于移动设备上的应用商店
* 修复了[18个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.29+is%3Aclosed)

### 2.0.26

* 修复了[5个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.26+is%3Aclosed)

### 2.0.25

* 处理在 Kubernetes/OpenShift 新增的 HTTPS only REST API 
* 修复了[这些问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.25+is%3Aclosed)

### 2.0.19

* 使用从 OpenShift/Kubernetes 的 go 源代码自动生成的 JSON 结构定义来为 REST API 提供忠实的 Jackson DTOs 定义
* 改进控制台的应用选项卡来展现更加美观的应用及 Pods 的详细列表
* 修复了[这些问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.19+is%3Aclosed)

### 2.0.18

* 修复了[这些问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.18+is%3Aclosed)

### 2.0.17

* 修复了[这些问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.17+is%3Aclosed)

### 2.0.15

* 修复了[这些问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.15+is%3Aclosed)

### 2.0.14

* 修复了[这些问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.14+is%3Aclosed)

### 2.0.12

* 增加了一个 camel-sql 快速入门，使用 Camel REST API 并显示在 API Registry / API 控制台
* 修复了[这些问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.12+is%3Aclosed)

### 2.0.11

* 更加友好的控制台包括
  * 如果 kibana 在运行中状态，可以提供Pods 到 Kibana 日志的深度链接
  * 你可以在控制器和服务页面浏览 Pods 的数量和他们的状态
  * 在控制器和服务页面提供到运行单控制器或单服务的 Pods 的链接
* 修复了[这些问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.11+is%3Aclosed)

### 2.0.10

* 修复了[12个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.10+is%3Aclosed)

### 2.0.9

* 移植 [API 控制台工作在 Kubernetes 之上](https://github.com/hawtio/hawtio/issues/1743)，以使 APIs 选项卡出现在 [Fabric8 控制台](http://fabric8.io/guide/console.html)上， 前提是在 Kubernetes 上运行 hawtio，并且运行着 [API 注册服务](https://github.com/fabric8io/quickstarts/tree/master/apps/api-registry)
* 增加 [Service wiring for Kubernetes](https://github.com/hawtio/hawtio/blob/master/docs/Services.md)，以使更加容易地动态链接导航条，按钮以及菜单项到运行在 Kubernetes 之上的远程服务（比如更好的链接到 Kibana，Grafana）
* 修复了[10个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.9+is%3Aclosed)

### 2.0.8

* 修复了[5个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.8+is%3Aclosed)

### 2.0.7

* 修复了[4个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.7+is%3Aclosed)

### 2.0.6

* 修复了[这些问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.6)

### 2.0.5

* 修复了[这些问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.5+is%3Aclosed)

### 2.0.2

* [控制台](http://fabric8.io/guide/console.html)布局与图标更加好看（并且 Wiki 选项卡现在称为 Library）
* 修复了[5个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.2+is%3Aclosed)

### 2.0.1

* 改进了[应用压缩包](http://fabric8.io/guide/appzip.html)被部署到（或者拖拽到)[控制台](http://fabric8.io/guide/console.html) 的 Wiki 选项卡时的展现
* 修复了[5个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.1+is%3Aclosed)

### 2.0.0

* 首个 [基于 Kubernetes 的 Fabric8 发布](http://fabric8.io/guide/overview.html)，重用了标准 [Kubernetes](http://kubernetes.io/) REST APIs 进行容器编排，以及使用 [Docker 容器镜像](http://docker.com) 或者 [Jube 镜像压缩包](http://fabric8.io/jube/imageZips.html) 进行容器构建
* 修复了[8个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A2.0.0)

### 1.2.0.Beta5

* Profile 的名字必须是小写文字

### 1.2.0.Beta4

* 改进了启动体验，使 fabric8 环境构建完成更明显
* 改进了 REST API，使你更容易浏览容器 Profile，开始/停止/删除容器，提交新的 Profile 到版本管理，或者删除 Profile
* 修复了[60个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A1.2.0.Beta4)

我们在迁移到 CXF 3.x 之前，REST API 是在 http://localhost:8181/cxf/fabric8 访问的，而不是更通常的 http://localhost:8181/api/fabric8 - 你总是能够通过使用 **fabric:info** CLI 命令来找到它。

### 1.2.0.Beta3

* 修复了在 docker 中运行 fabric8，以及在 docker 中创建容器存在的问题
* 修复了[12个问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A1.2.0.Beta3)

### 1.2.0.Beta2

* 升级 [Apache Karaf](http://karaf.apache.org/) 到 2.4.x 版本，以使我们在所有的 MBeans，OSGi 服务以及 CLI 命令中获得完整的基于角色的访问控制（RBAC）支持
* 容器名称必须只能是小些文字
* 改进 [Auto Scaling](http://fabric8.io/gitbook/requirements.html) UI 来使 [Auto Scaling 需求](http://fabric8.io/gitbook/requirements.html)的配置更容易
* 改进了 Web 控制台的 Profile 页面的配置选项卡，以使配置所有容器是否是运行中，以及它们是否实际使用了 OSGi 的工作更加容易
* 增加了新的 [Arquillian](http://fabric8.io/gitbook/arquillian.html) 集成测试框架来使远程或者基于 docker 的 fabrics 上的测试更容易
* 修复了各种问题，比如 Java containers, Tomcat and Docker
* 修复了[这些问题](https://github.com/fabric8io/fabric8/issues?q=milestone%3A1.2.0.Beta1+is%3Aclosed)

### 1.1.0.CR5

* 当[ ssh hosts 在 json 中被指定](https://github.com/fabric8io/fabric8-devops/blob/master/autoscaler/ssh-mq-demo.json#L29)为像[这个示例](https://github.com/fabric8io/fabric8-devops/tree/master/autoscaler)一样时，[AutoScaler](http://fabric8.io/gitbook/requirements.html) 现在可以适当地重新创建 ssh 容器。并且提供一个新的 **autoscale-status** CLI 命令来查看 [AutoScaler](http://fabric8.io/gitbook/requirements.html) 的运行状况
* 修复了[56个问题和功能增强](https://github.com/fabric8io/fabric8/issues?milestone=11&state=closed)

### 1.1.0.CR3

* 在 Web 控制台提供了新的顶层 Profiles 选项卡，可以方便地浏览与参看所有的 Profiles，能够按照带有图标和摘要的文本或标签进行过滤。
  摘要文本来自于图标（svg,png,jpg）和 wiki 的`Summary.md`文件
* 首个 Fabric DNS 支持
* 如果进程被明示地杀死，[AutoScaler](http://fabric8.io/gitbook/requirements.html) 现在可以适当地重新创建 [Java 容器](http://fabric8.io/gitbook/javaContainer.html) 和 [Process 容器](http://fabric8.io/gitbook/processContainer.html) 实例
* 命名为 [amq: endpoint](http://fabric8.io/gitbook/camelEndpointAmq.html), mq-fabric-camel 的特性被改名为对于 camel 特性名称更为通用的 camel-amq
* 向 Tomcat, TomEE, Jetty or WildFly 部署 WARs 现在可以拥有它们自己的上下文路径配置。 通过配置 maven 插件的 [webContextPath](http://fabric8.io/gitbook/mavenPlugin.html#property-reference) 属性或在 [io.fabric8.web.contextPath.properties 文件](https://github.com/fabric8io/fabric8/blob/master/fabric/fabric8-karaf/src/main/resources/distro/fabric/import/fabric/profiles/containers/drools/execution.server.profile/io.fabric8.web.contextPath.properties#L2-2)实现
* 修复了[132个问题和功能增强](https://github.com/fabric8io/fabric8/issues?milestone=10&page=1&state=closed)

### 1.1.0.CR2

* 重命名 CLI 命令 `fabric:profile-download` 为 `fabric:profile-download-artifacts`
* 修复了[165个问题和功能增强](https://github.com/fabric8io/fabric8/issues?milestone=7&state=closed)

### 1.1.0.CR1

* 为[微服务](http://fabric8.io/gitbook/microServices.html)和 [Spring Boot](http://fabric8.io/gitbook/springBootContainer.html)提供了可用的 [Java 容器](http://fabric8.io/gitbook/javaContainer.html) 
* 提供了强大的 [Spring Boot](http://fabric8.io/gitbook/springBootContainer.html) 集成
* 支持将 Apache Tomcat， TomEE 和 Jetty 作为 web 容器
* 集成了 [fabric:watch *](http://fabric8.io/gitbook/developer.html#rad-workflow) 和各种容器，比如  [Java Container](http://fabric8.io/gitbook/javaContainer.html), [Spring Boot](http://fabric8.io/gitbook/springBootContainer.html), Tomcat, TomEE, Jetty
* 更多的[快速入门实例](http://fabric8.io/gitbook/quickstarts.html)，全部都包含在[发布](http://fabric8.io/gitbook/getStarted.html)中，并且改变为原型
* 增加了新的[持续部署命令](continuousDeployment.md)，比如 _profile-import_, _profile-export_ 和改进的  [mvn fabric8:zip 目标来服务于多模块项目](http://fabric8.io/gitbook/mavenPlugin.html)
* 修复了[136个问题和功能增强](https://github.com/fabric8io/fabric8/issues?milestone=6&state=closed)

### 1.1.0.Beta6

* 修复了[176个问题和功能增强](https://github.com/fabric8io/fabric8/issues?milestone=5&state=closed)

### 1.1.0.Beta5

* 修复了[113个问题和功能增强](https://github.com/fabric8io/fabric8/issues?milestone=8&state=closed)

### 1.1.0.Beta4

* 启动容器的脚本现在为 **bin/fabric8** ，并且除非你明示配置 [fabric8 环境变量](http://fabric8.io/gitbook/environmentVariables.html)，否者它默认会创建一个 构造（fabric）
* 添加了新的 [maven 插件目标](http://fabric8.io/gitbook/mavenPlugin.html) (fabric8:agregate-zip, fabric8:zip, fabric8:branch)
* 提供全面可用的 [docker 支持](http://fabric8.io/gitbook/docker.html)，所以使用 docker profile，你可以使用 docker 创建容器
* 修复了[300个问题和功能增强](https://github.com/fabric8io/fabric8/issues?milestone=9&state=closed)

### 1.0.0.x

* 首个社区发布集成到 [JBoss Fuse 6.1 产品](http://www.jboss.org/products/fuse)
* 采用 [hawtio](http://hawt.io/) 作为控制台
* 使用 git 进行配置， 确保所有变更得到审计和版本管理，并使版本回退变得容易