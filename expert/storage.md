# 插件编译

{% hint style="info" %}
**提示：** 本信息面向开发者。请先学习如何使用 Java！
{% endhint %}

### 设置 IDE

如果您想在不使用 GitHub 在线工具的情况下[提交 Pull Request](https://github.com/PikaMug/Quests/pulls)，或者只是想为自己修改插件的某些部分，最好的方法是在本地机器上编译插件。

虽然可以使用多种程序完成此操作，但我们推荐使用 [IntelliJ IDEA](https://www.jetbrains.com/idea/)。建议对 Apache Maven 有基本的了解。

### 下载源代码

在您的机器准备就绪后，我们来下载 Quests 的源代码。如果您打算提交 Pull Request，建议先[创建一份 fork](https://guides.github.com/activities/forking/)，这样您可以将自己的修改请求合并到主仓库中。如果您只是想在本地编译并应用自己的修改，可以直接复制以下链接：

`https://github.com/PikaMug/Quests.git`

打开 IntelliJ IDEA。如果您当前正在打开一个项目，请前往 `File -> Close Project`。在 IntelliJ IDEA 欢迎界面，点击 **Get from VCS** 按钮。将上面的 URL 粘贴进去，然后点击 **Clone**。等待项目加载完成，然后在左侧任务栏中查看 Project 视图。

### 分享修改

在您完成想要的修改后，就可以选择打包插件，或者将修改上传到您的 fork 仓库。

**将 Quests 编译成 jar 文件**（用于 Spigot/Paper 服务器）：  
在右侧任务栏打开 Maven 视图，展开 `quests (root)`，然后选择 `package` 选项。剩余的依赖项会自动下载完成，编译成功后（在 Windows 系统下），您会在以下路径找到生成的 JAR 文件：

`C:\Users\您的用户名\IdeaProjects\Quests\dist\target`

**上传修改**（用于后续提交 Pull Request）：  
在左侧任务栏打开 Commit 视图。确保您想要提交的所有文件都已被勾选，然后为本次提交写一个简短的描述。确认一切无误后，点击 **Commit and Push...** 按钮，并按照提示完成操作。

访问您在 GitHub 上的 fork 仓库，点击 **New pull request** 按钮，请求将您的提交合并到 Quests 主仓库中。按照屏幕上的指引操作即可。感谢您为 Quests 做出贡献！