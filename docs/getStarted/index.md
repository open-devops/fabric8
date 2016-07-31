## 入门

### OpenShift / Kubernetes 安装

在你开始使用 fabric8 之前，你将会需要一个 Kubernetes 或者 OpenShift 集群。这里有一些选项信息:

#### 已经有一个可工作的 Kubernetes 集群？

如果你已经有了一个安装好的集群，可以参考以下信息:

* [**Kubernetes**](kubernetes.html): 如果你有一个可工作的 [Kubernetes](http://kuberentes.io) 集群，可以使用[这个指南来安装 fabric8](kubernetes.html)

* [**OpenShift**](openshift.html): 如果你有一个可工作 [OpenShift V3](http://www.openshift.com) 集群，可以使用[这个指南来安装 fabric8](openshift.html)


#### 还没有一个 Kubernetes 集群？

* [**MiniKube**](minikube.html)

  这是最快最容易的方式来本地安装 Fabric8 和 Kubernetes。
  你只需要下载2个二进制文件（[minikube](https://github.com/kubernetes/minikube/releases) 和 [gofabric8](https://github.com/fabric8io/gofabric8/releases)） - 无需 VirtualBox 或 Vagrant！
  查看如何[在 MiniKube 创建的 Kubernetes 集群上安装 Fabric8](minikube.html)

* [**MiniShift**](minishift.html)

  这是最快最容易的方式来本地安装 Fabric8 和 OpenShift Origin。
  你只需要下载2个二进制文件（[minishift](https://github.com/jimmidyson/minishift/releases) and [gofabric8](https://github.com/fabric8io/gofabric8/releases)） - 无需 VirtualBox 或 Vagrant！
  查看如何[在 MiniShift 创建的 OpenShift Origin 集群上安装 Fabric8](minishift.html)

* [**Vagrant 与 Kubernetes**](vagrant-kubernetes.html)

  如果你已经安装了 Vagrant 和 VirtualBox，并想在本地将他们和 Fabric8 与 Kubernetes 一起使用，那个这个选项适合你。
  你所需要的是本地安装了 [Vagrant](https://www.vagrantup.com/) 和 [VirtualBox](https://www.virtualbox.org/)。
  查看如何[创建 Kubernetes 的 Fabric8 Vagrant 镜像](vagrant-kubernetes.html)

* [**Vagrant 与 OpenShift Origin**](vagrant.html)

  如果你已经安装了 Vagrant 和 VirtualBox，并想在本地将他们和 Fabric8 与 OpenShift Origin 一起使用，那个这个选项适合你。
  你所需要的是本地安装了 [Vagrant](https://www.vagrantup.com/) 和 [VirtualBox](https://www.virtualbox.org/)。
  查看如何[创建 OpenShift Origin 的 Fabric8 Vagrant 镜像](vagrant.html)

* [**CDK**](cdk.html) - 使用红帽容器开发工具包

  你需要本地安装 [Vagrant](https://www.vagrantup.com/) 和 [VirtualBox](https://www.virtualbox.org/)，以及[一些前提条件](https://github.com/redhat-developer-tooling/openshift-vagrant#prerequisites)。
  参看如何[在 CDK Vagrant 镜像中安装 Fabric8](cdk.html)

#### 使用公有云？

* [**Google Container Engine**](gke.html) - Kubernetes

  [Google Container Engine](https://cloud.google.com/container-engine/) (GKE) 是 Google 托管的 Kubernetes 平台。虽然在 Kubernetes [入门](http://kubernetes.io/gettingstarted/)页面列出了很多安装 Kubernetes 的其他方法 ， 但是如果你想无需准备基础设施来快速安装运行，GKE 是个很好的选项。这个[指南](gke.html)会帮助你一步一步地使用 GKE 托管的纯粹 Kubernetes 安装 fabric8。

#### 本地客户端安装

为了流畅的开发者体验及使用 fabric8 [工具](../tools.html)，你需要在本地安装一个 OpenShift 客户端，在这个[安装方法](local.html)中描述了如何做到这一切。

### 下一步

* [运行一个 fabric8 应用](apps.html)
* [查看快速入门示例](../quickstarts/index.html)
* [学习如何在本地开发应用程序](develop.html)
* [在 iPaaS 上运行快速入门示例](example.html)

### 故障诊断

希望这些信息能够帮助你快速起步，如果你遇到任何问题，查看[问题集](http://fabric8.io/guide/FAQ.html)，[取得联系](http://fabric8.io/community/index.html) 或者 [提交问题](https://github.com/fabric8io/fabric8/issues)

也可以查看[故障诊断指南](troubleshooting.html)
