
我们热爱贡献! 我们真的需要你的帮助使得[ fabric8 更出色](http://fabric8.io/), 所以请[加入我们的社区](/community/index.html)!

非常感谢我们所有的[现有贡献者](https://github.com/fabric8io/fabric8/graphs/contributors)! 为什么不加入并帮助我们呢?

以下为一些帮助你入门的注意事项:

## 入门

* 确保你有一个[GitHub账户](https://github.com/signup/free) ，应为你会需要它来提交问题，注释或拉取请求。
* 已经有任何能够帮助我们改进fabric8的想法？ 请将你的想法[提交为一个问题](https://github.com/fabric8io/fabric8/issues?state=open)。 我们很欣赏建设性批评。
* 喜欢提交我们能够连接的博客投稿，文章，或者截屏视频？ 只要[提交为一个问题](https://github.com/fabric8io/fabric8/issues?state=open)，我们就会将它合并到我们的网站上。
* 检索我们的[问题追踪系统](https://github.com/fabric8io/fabric8/issues?state=open)，查看是否已经有你在考虑的任何想法或问题，如果已经有的话，请在评论区加入交流。
* 提交任何问题，特性请求或者改进想法到我们的[问题追踪系统](https://github.com/fabric8io/fabric8/issues?state=open)。
  * 当提交缺陷问题时，请包括再现步骤，清晰地描述问题。
  * 确保填写到你所知道有问题的最早版本上。
  
### 喜欢破解一些代码？

* 如果你喜欢和代码打交道，查看以下问题列表：
   * 如果你喜欢更具挑战性， 请查看[所有待解决问题](https://github.com/fabric8io/fabric8/issues?state=open)。

* 你需要复刻仓库来修改代码。我们欢迎任何类似以下的贡献:
   * 修复拼写错误
   * 改善文档或内嵌帮助
   * 编写新的测试用例或改善现有用例
   * 添加新的特性
   
## 提交变更到 fabric8

遵循以下流程是使你的工作被反映到项目中的最好方式：

1. [复刻](https://help.github.com/fork-a-repo/)项目, 
  克隆你的复刻仓库, 并且配置上游仓库的远程地址:

   ```bash
   # 克隆你的复刻仓库到当前目录
   git clone https://github.com/<your-username>/fabric8.git
   # 切换到新克隆的目录
   cd fabric8
   # 将上游仓库的远程地址配置并命名为 upstream
   git remote add upstream https://github.com/fabric8io/fabric8.git
   ```

2. 如果你的克隆已经有一段时间了，可以通过以下方式从上游仓库获得最近变更:

   ```bash
   git checkout master
   git pull upstream master
   ```

3. 创建一个新的主题分支（在项目开发主线之外）来承载你的特性，变更，修复开发：

   ```bash
   git checkout -b <topic-branch-name>
   ```

4. 按照逻辑性整理信息来提交你的变更。如果你有很多提交，你可以使用 Git 的[交互式变基](https://help.github.com/articles/interactive-rebase) 特性来在发布提交之前整洁你的提交。
   如果你的变更参照了一个既有[问题](https://github.com/fabric8io/fabric8/issues?state=open)，
   在提交消息中请使用"fixes #123"（使用正确的问题编号）。

5. 文档的变更被定位在 [docs](docs) 目录下。花些时间考虑一下你的代码变更是否应该反映到文档中。
  你也许需要更新既有主题，或者通过添加一个新的 `.md` 文件来创建一个新的主题。
  新文件应该被添加到 [summary](docs/SUMMARY.MD) 文件的目录表中。

6. 合并（或变基） 上游开发分支到你的本地主题分支上:

   ```bash
   git pull [--rebase] upstream master
   ```

7. 推送你的主题分支到你的复刻仓库中:

   ```bash
   git push origin <topic-branch-name>
   ```

8. [打开一个拉取请求](https://help.github.com/articles/using-pull-requests/)，确保对比`master`分支具有明确的标题和描述。

**重要**: 当提交一个补丁时，你同意让项目所有者在[Apache许可证](license.txt)条款下授权你的工作成果。


# 补充资源

* [fabric8 问题集](http://fabric8.io/faq/index.html)
* [GitHub 帮助文档](http://help.github.com/)
* [GitHub 创建拉取请求文档](https://help.github.com/articles/creating-a-pull-request)
* [加入 fabric8 社区](http://fabric8.io/community/index.html)

