# 插件编译

{% hint style="info" %}
**注意：** 此信息面向开发者。请先学习 Java 基础知识！
{% endhint %}

### 设置 IDE

如果您希望[提交 Pull Request](https://github.com/PikaMug/Quests/pulls) 而不想使用 GitHub 的在线工具，或者只是想为自己修改插件的某些部分，最好的方式是在本地机器上编译插件。

虽然可以使用多种程序完成此操作，但我们推荐使用 [IntelliJ IDEA](https://www.jetbrains.com/idea/)。建议对 Apache Maven 有基本了解。

### 下载源码

准备好您的机器后，我们来下载 Quests 源码。如果您打算提交 Pull Request，推荐先[创建 fork](https://guides.github.com/activities/forking/)，这样您就可以请求将更改合并到主仓库中。如果只是想在本地编译并进行个人修改，请复制以下链接：

`https://github.com/PikaMug/Quests.git`

打开 IntelliJ IDEA。如果当前正在某个项目中，请转到 `File -> Close Project`。在欢迎界面点击 **Get from VCS** 按钮。粘贴上面的 URL，然后点击 **Clone**。给项目一些时间加载完成，随后在左侧任务栏中探索项目视图。

### 分享修改

完成所需的更改后，您可以选择将其打包为 jar 文件，或上传到您 fork 的仓库中。

**编译 Quests 为 jar 文件**，以便在 Spigot/Paper 服务器中使用：在右侧任务栏打开 Maven 视图，展开 `quests (root)`。选择 `package` 选项。剩余的依赖项将会自动下载，（在 Windows 系统上）最终完成的 JAR 文件将位于 `C:\Users\YourAccount\IdeaProjects\Quests\dist\target`。

**上传更改**，以便后续用于 Pull Request：在左侧任务栏打开 Commit 视图。确保所有您想要提交的文件都被勾选，然后为本次提交填写一个简短的描述。当您完全确定要与大家分享更改时，选择 `Commit and Push...` 按钮并按照提示操作。

访问您在 GitHub 上的 fork 仓库，点击 `New pull request` 按钮，请求将新提交合并到主 Quests 仓库。按照页面提示操作。感谢您为 Quests 做出贡献！