## Kubernetes Client API

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.fabric8/kubernetes-api/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/io.fabric8/kubernetes-api/)
[![Javadocs](http://www.javadoc.io/badge/io.fabric8/kubernetes-api.svg?color=blue)](http://www.javadoc.io/doc/io.fabric8/kubernetes-api)

这个类库使用 JAXRS 2.0 提供一个 Java [Kubernetes](http://kubernetes.io/) 客户端 API。

### 将它添加到你的 Maven pom.xml

为了能够在你的基于 [Apache Maven](http://maven.apache.org/) 项目中使用这个 Java 类库，请将以下定义添加到你的 pom.xml 文件中

            <dependency>
                <groupId>io.fabric8</groupId>
                <artifactId>kubernetes-api</artifactId>
                <version>2.2.101</version>
            </dependency>

### 试例

如果你复制源代码:

    git clone https://github.com/fabric8io/fabric8.git
    cd fabric8

并且如果你正在运行 Kubernetes (比如[试运行 fabric8](http://fabric8.io/guide/getStarted.html))，以使 $KUBERNETES_MASTER 指向 Kubernetes REST API，那么以下应该正常工作:

    cd components/kubernetes-api
    mvn clean test-compile exec:java

这个示例程序应该正常启动并且列出一些 Kubernetes Pods。

### API 概述

你使用 **DefaultKubernetesClient** 去创建 [Kubernetes Client](https://github.com/fabric8io/kubernetes-client) 的一个实例，它支持 [Kubernetes REST API](https://github.com/GoogleCloudPlatform/kubernetes/blob/master/DESIGN.md#kubernetes-api-server)。

样例:

    KubernetesClient kube = new DefaultKubernetesClient();
    PodList pods = kube.pods().list();
    for (Pod pod : pods.getItems()) {
        String name = pod.getMetadata().getName();
        String ip = pod.getStatus().getPodIP();
    }

**KubernetesClient** 默认使用 **KUBERNETES_MASTER** 环境变量。

如果你的 Java 代码是运行在 Kubernetes 环境中的话， KubernetesClient 会默认使用 **kubernetes.default.svc** （被 **KUBERNETES_MASTER** 设定覆盖） 作为和[kubernetes 服务](http://fabric8.io/guide/services.html) REST API 通信的地址。

如果你希望在你的 Java 代码中使用特定的 URL，你只需将它传给工厂构造体函数即可。（虽然通常你不需要这么做）

    KubernetesClient kube = new DefaultKubernetesClient("http://localhost:8585/");
    PodList pods = kube.pods().list();

想看更多的使用 [Kubernetes Client](https://github.com/fabric8io/kubernetes-client) 访问 Kubernetes API 的信息，可以看一下[这个示例](https://github.com/fabric8io/fabric8/blob/master/components/kubernetes-api/src/test/java/io/fabric8/kubernetes/api/Example.java#L48)。

### 配置

所有配置都通过以下环境变量:

* `KUBERNETES_MASTER` - Kubernetes Master 的位置 
* `KUBERNETES_NAMESPACE` - 操作中使用的默认 Kubernetes 命名空间
* `KUBERNETES_CERTS_CA_DATA` - 完整的 Kubernetes CA 证书字符串 （`KUBERNETES_CERTS_CA_DATA` 和 `KUBERNETES_CERTS_CA_FILE` 只应指定一个)
* `KUBERNETES_CERTS_CA_FILE` - Kubernetes CA 证书文件路径（`KUBERNETES_CERTS_CA_DATA` 和 `KUBERNETES_CERTS_CA_FILE` 只应指定一个)
* `KUBERNETES_CERTS_CLIENT_DATA` - 完整的 Kubernetes 客户端证书字符串（`KUBERNETES_CERTS_CLIENT_DATA` 和 `KUBERNETES_CERTS_CLIENT_FILE` 只应指定一个）
* `KUBERNETES_CERTS_CLIENT_FILE` - Kubernetes 客户端证书文件路径（`KUBERNETES_CERTS_CLIENT_DATA` 和 `KUBERNETES_CERTS_CLIENT_FILE` 只应指定一个）
* `KUBERNETES_CERTS_CLIENT_KEY_DATA` - 完整的 Kubernetes 客户端私钥字符串（`KUBERNETES_CERTS_CLIENT_KEY_DATA` 和 `KUBERNETES_CERTS_CLIENT_KEY_FILE` 只应指定一个）
* `KUBERNETES_CERTS_CLIENT_KEY_FILE` - Kubernetes 客户端私钥文件路径（`KUBERNETES_CERTS_CLIENT_KEY_DATA` 和 `KUBERNETES_CERTS_CLIENT_KEY_FILE` 只应指定一个）
* `KUBERNETES_TRUST_CERTIFICATES` - 是否信任 Kubernetes 服务器证书（由于不是安全的方式，如果有可能请尽量使用其他环境变量适当地配置证书）

`*_DATA` 变量优先于 `*_FILE` 变量。

#### OpenShift 默认值

如果没有通过明示的代码或者环境变量进行配置，`kubernetes-api` 类库会尝试解析用户的 `~/.kube/config` 文件来找到当前登录凭证和命名空间。

这意味着，如果你使用 [OpenShift](http://www.openshift.org/) 命令行工具 `oc`，你能够登录和切换项目（也即 Kubernetes 的命名空间）， `kubernetes-api` 类库会默认使用这些信息。

比如

```
oc login
oc project cheese
mvn fabric8:apply
```

上例中，如果当前环境中没有 `KUBERNETES_NAMESPACE` 环境变量，或者叫做 `fabric8.apply.namespace` 的 Maven 属性，`fabric8:apply` 目标会将 Kubernetes 资源运用到 `cheese` 命名空间。
