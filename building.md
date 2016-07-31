构建 Fabric8
============

由于一些插件的依赖关系，构建 Fabric8 需要 3.2.5 以上版本 Maven。

首先，Fabric8 构建进程可能需要比默认分配给 Maven 进程的内存更多的内存。
因此，在开始之前确认 MAVEN_OPTS 系统属性设定如下：

    > MAVEN_OPTS="-Xmx1024m -XX:MaxPermSize=512m"

构建 Fabric8 并运行关联的测试用例：

    > mvn clean install

快速构建
==========

你可以通过添加 `-DskipTests` 进行快速构建。

构建 Fabric8 并跳过测试执行

    > mvn clean install -DskipTests

构建 fabric8 的所有模块，但跳过测试执行

测试 Maven Profiles
==========

Fabric8 测试被分布在不同的专属测试 Maven Profiles 中。

* ts.all:    包括附加测试

实例
--------
  
构建 Fabric8 并运行定常测试

    > mvn clean install

构建 Fabric8 并运行所有测试

    > mvn clean install -Dts.all
    

在构建中包括快照
============================

Fabric8 容许通过 Maven Profiles 来使用  hawtio / Camel 快照构建。

* camelSnapshot
* hawtioSnapshot

比如使用最新 hawtio 去快照来构建 Fabric8 并运行关联的测试用例：

    > mvn -Phawtio-snapshot clean install

注意, 为了避免被提示输入 gpg 键，可添加 **-Dgpg.skip=true**


许可证检查
=============

源代码使用根目录下的许可证头文件  ```fabric-license-header.txt```。

你可以运行根目录的以下 Maven 目标来检查源代码的许可证缺失。 注意这会检查所有的源代码:

    > mvn com.mycila:license-maven-plugin:2.6:check -Dlicense.header=fabric-license-header.txt

对于任何子模块，你需要使用相对路径来参照许可证文件:

```
   > cd components
   > mvn com.mycila:license-maven-plugin:2.6:check -Dlicense.header=../fabric-license-header.txt 
```

你可以使用 ```format``` 目标来更新源代码的许可证信息，比如:

    > mvn com.mycila:license-maven-plugin:2.6:format -Dlicense.header=../fabric-license-header.txt 


GitBook
=======

这个文档使用 [GitBook](https://github.com/GitbookIO/gitbook) 来编译成书。

首先使用 npm 安装 gitbook

    npm install -g gitbook

然后安装 anchor 插件

    sudo npm install -g gitbook-plugin-anchors    

注意在 osx 上你也许需要使用 `sudo` 来运行这些命令。

然后在本地编译成书

    cd docs
    gitbook serve ./

从浏览器访问此书

    http://localhost:4000

如果需要在 gitbook 中添加新的章节，请编辑 `docs/SUMMARY.md` 文件。