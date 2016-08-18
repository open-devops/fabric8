## 创建微服务

为项目配置流水线的最容易的方式为使用 [Fabric8 开发者控制台](../console.html)。

当打开 Fabric8 控制台时，你应该能够看到以下页面：

![Fabric8 开发者控制台: 开始页面](../images/console-home.png)

`Team（团队）` 是一个 Kubernetes 命名空间，用来运行你的开发工具（比如 Jenkins, Nexus, JBoss Forge），并和好些环境关联（测试，预发布，生产环境）。

点击 `Team Dashboard（团队仪表盘）` 可以把你带到团队仪表盘页面，在这里你能够创建新的应用或者浏览你的既存应用：

![Fabric8 开发者控制台: 团队仪表盘](../images/console-dashboard.png)

如果你点击 `Create Application（创建应用）`，你会进入创建应用向导页面：

![Fabric8 开发者控制台: 创建应用](../images/create-project.png)

然后你可以选择你希望创建的项目类型和项目名称：

![Fabric8 开发者控制台: 选择项目类型](../images/create-app.png)

然后选择你的[自动交付流水线](cdelivery.html)：

![Fabric8 开发者控制台: Choose CD Pipeline](../images/console-pick-pipeline.png)

如何你选择 `Copy pipeline to project（拷贝流水线到项目）`， 那么定义了流水线的 Jenkinsfile 会被拷贝到你的项目的 Git 仓库中，这样你可以方便地像变更其他代码一样在版本管理系统中编辑它。

现在你会进入到 `App Dashboard（应用仪表盘）` 页面，在这里你可以统一看到所有的环境和活动流水线，以及最近提交的构建状况。下图展现了在金丝雀发布，测试和预发布完成后，等待生产环境上线的审批状态。

![Fabric8 开发者控制台: 应用仪表盘](../images/console-app-dashboard.png)

你可以点击 `Proceed（继续执行）` 按钮来将发布提升到生产环境，或者 `Abort（放弃）` 按钮来停止流水线。

你可以通过页面右上角的工具下拉菜单，很容易地在所有你的开发工具（Gogs, Jenkins, Nexus 等） 间切换。 

![通过点击工具下拉菜单来查看开发的应用](../images/console-tools.png)

### 运行时标签页

`Team（团队）` 页面有一个 `Runtime（运行时）` 标签页，在这里你可以浏览你的开发环境的运行时状态。你也可以在主页点击环境页面来浏览它的运行时。

`Runtime（运行时）` 页面有很多标签页来让你和 Kubernetes 的各种资源一起工作。我们重点介绍几个你会需要使用的标签页：

#### Replicas（副本）

**Replicas（副本）** 标签页可以帮助你了解你的系统正在运行什么服务，它会显示 Kubernetes 上的所有 [Replication Controllers（副本控制器）](replicationControllers.html) 或者 ReplicaSets （副本集）。

为了扩大或缩小控制器规模来运行更多或更少的 [Pods](pods.html)（容器），只需要增加或减少 **Desired Replicas（副本期待值）** 设定值并点击保存按钮，然后 Pods 就会像是变戏法一样被创建出来，或者被销毁掉。

![控制器标签页截屏](../images/controllers.png)

#### Overview（概览）

概览标签页可以帮助你了解所有的各类[服务](services.html)和[副本控制器](replicationControllers.html)之间的交互：

![概览标签页截屏](../images/overview.png)


### 演示 

这里有一个[描述如何创建微服务并通过持续交付流水线来部署和编辑微服务的视频](https://vimeo.com/170830750)。

<div class="row">
  <p class="text-center">
      <iframe src="https://player.vimeo.com/video/170830750" width="1000" height="562" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>
  </p>
  <p class="text-center">
    <a href="https://medium.com/fabric8-io/create-and-explore-continuous-delivery-pipelines-with-fabric8-and-jenkins-on-openshift-661aa82cb45a">更详细的信息请参见博客投稿</a>
  </p>
</div>