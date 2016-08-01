## 使用 Kubernetes 的 Fabric8 Vagrant 镜像 

This is the fastest way to get going with Fabric8 and Kubernetes on your laptop.

 ### How to vagrant up

 * 下载并安装 [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
 * 下载并安装 [Vagrant](http://www.vagrantup.com/downloads.html)

 现在复制
 [fabric8 安装程序 的 git 仓库](https://github.com/fabric8io/fabric8-installer)
 并执行以下命令:

 ```sh
 $ git clone https://github.com/fabric8io/fabric8-installer.git
 $ cd fabric8-installer/vagrant/kubernetes
 ```

 取决于你的宿主机操作系统，你需要安装一个额外的 Vagrant 插件:

 * Linux 和 OS X： `vagrant plugin install landrush` 
 * Windows： `vagrant plugin install vagrant-hostmanager` 

 现在启动 Vagrant 虚拟机。

 ```sh
 vagrant up
 ```

Vagrant 镜像默认配置为 2 CPU 内核及 4G 内存。 通常建议不要超过你机器资源的一半，当你的机器上有足够的资源时，你可以编辑 `Vagrantfile` 文件来增加设定值。这个设定定义在文件的底部：

 ```ruby
 v.cpus = 2
 ```

 变更虚拟机的内存使用量时，你可以使用环境变量。比如运行 `cd-pipeline` 应用程序时，我们推荐使用 8G 内存：
 ```
 export FABRIC8_VM_MEMORY=8192
 ```

 接下来按照屏幕上的指示

 * 你现在应该有一个在网络地址 `172.28.128.80` 或  `vagrant.k8s` 上运行的 Vagrant 镜像
   
 * 下载 Docker 镜像可能会花一些时间，你也许想先跳到[本地安装](local.html)环节，完成后再回到这里
 * 在 Vagrant Box 创建及 Docker 镜像下载后，[fabric8 控制台](../console.html)应该出现在  [http://172.28.128.80:8080/api/v1/proxy/namespaces/default/services/fabric8/](http://172.28.128.80:8080/api/v1/proxy/namespaces/default/services/fabric8/)
 * 如果提示你输入一个登录用户和登录密码，使用 `admin` 和 `admin`
 * 你现在应该在 fabric8 主控制台！ 多容易！ :)
 * 创建新的应用时，选择`团队仪表盘`，它通常被称为`默认`，但也可能是你的 Kubernetes 集群中的默认命名空间

 ### 安装其他应用程序

当你在 [fabric8 控制台](http://fabric8.io/guide/console.html)的团队或命名空间的`运行时`视图中，点击`运行...`按钮。

 这会列出所有已安装的 [OpenShift 模板](http://docs.openshift.org/latest/dev_guide/templates.html)

 * 要运行任何已安装的模板，只需点击`运行`按钮（绿色播放按钮）
 * 要通过命令行安装其他应用程序，你可以使用 Vagrant 镜像中的 `gofabric8` 程序。比如安装完整的 [Fabric8 微服务平台管理支持](../management.html)时使用以下命令：

 ```
 gofabric8 deploy -y --domain=vagrant.f8 --app=management
 ```

 * 安装新的[OpenShift 模板](http://docs.openshift.org/latest/dev_guide/templates.html)或者其他 Kubernetes 资源只需拖拽 JSON 文件到 `运行...` 页面！
 * 你可以下载
   [fabric8 模板 2.2.101 发行版](http://repo1.maven.org/maven2/io/fabric8/devops/distro/distro/2.2.101/distro-2.2.101-templates.zip)，
   解压并拖拽你想要的 JSON 文件来安装到
   [fabric8 控制台](http://fabric8.io/guide/console.html)，它们应该出现在 `运行...` 页面
 * 你可以使用[ helm 命令行工具](http://fabric8.io/guide/helm.html)安装或升级应用程序
 * 你也可以通过 **oc** 命令行工具来安装其他 OpenShift 模板 或 Kubernetes 资源：
 ```
     kubectl create -f jsonOr YamlFileOrUrl
 ```
  * 一般来说，各种应用程序的默认用户名／密码是 `admin/admin` 或 `gogsadmin/RedHat$1`。 在流水线和 GOGS 一起工作需要输入凭证时可尝试这些。

 ### 设定你的本地机器

 为了从你的本地主机和 Vagrant 虚拟机一起通信，推荐安装 kubectl 客户端工具。 这在额外的[文档](local.html)中有解释。

 这对使用 [fabric8 Maven 工具](../mavenPlugin.html)或重用 Vagrant 中的 Docker Daemon 也有帮助；以使所有构建的镜像在 OpenShift 环境里面都可以被访问到。

 要不然你也可以通过 `vagrant ssh` 登陆到 Vagrant 虚拟机。 虚拟机中也安装了 kubectl 工具。

 ### 刷新镜像

 注意: 如果你已经运行了上面的镜像并想更新到最新的 Vagrant 和 Kubernetes 及 Fabric8 镜像发布版本，你需要销毁和重新创建 Vagrant 镜像。你可以使用以下方法：

 ```sh
 vagrant destroy -f
 git pull
 vagrant up
 ```

 ### 故障诊断

 查看[故障诊断指南](troubleshooting.html)获得更多的帮助。
