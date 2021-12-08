# Plugin Compilation

{% hint style="info" %}
**Alert:** This information is intended for developers. Learn how to use Java first!
{% endhint %}

### Set up an IDE

If you would like to [submit a Pull request \(PR\)](https://github.com/PikaMug/Quests/pulls) without the use of Github's online tools, or would just like to change some aspects of the plugin for yourself, the best way to do so is to compile the plugin locally on your own machine.

Although this can be accomplished in several programs, this guide will proceed using the popular Eclipse IDE _for Java Developers_. Get it from their official website at [https://www.eclipse.org/downloads/packages/](https://www.eclipse.org/downloads/packages/)

Once you've got Eclipse up and running, you'll need to install the EGit plugin in order to download the Quests source from Github. The easiest way to install it is to **drag** this Install link into Eclipse:

[![Drag to your running Eclipse\* workspace. \*Requires Eclipse Marketplace Client](https://camo.githubusercontent.com/0fbd492fb9bf92c1d58e3ee45589829afeda2533fb2c78244f9ef453437b888a/68747470733a2f2f692e696d6775722e636f6d2f3353694b7743632e706e67)](http://marketplace.eclipse.org/marketplace-client-intro?mpc_install=1336)

Alternatively, you can follow [these instructions](http://help.eclipse.org/2018-09/index.jsp?topic=/org.eclipse.platform.doc.user/tasks/tasks-127.htm) which will guide you through several windows for installation.

This project also requires the use of Maven _by Apache_. The included Maven integration that comes with Eclipse should be sufficient, but alternatively you could install a plugin like [M2Eclipse](https://www.eclipse.org/m2e/).

### Download the source code

With your machine raring to go, let's download the Quests source. If you intend on submitting a Pull request, we recommend [creating a fork](https://guides.github.com/activities/forking/) so that you can request that your changes be merged into this repository. Otherwise, if you only want to compile locally with your own edits, copy this link:

`git@github.com:PikaMug/Quests.git`

In Eclipse, click the Clone a Git Repository button. Look for it in this perspective added by EGit:

![](https://camo.githubusercontent.com/226a76f1c97e6e359c3bca7cd09ac92d81906b609cad743a4c1862d0d411c7af/68747470733a2f2f692e696d6775722e636f6d2f6c46374f7053552e706e67)

{% hint style="info" %}
**Pro-tip:** If you don't see the Git Repositories perspective, go to `Window -> Open Perspective -> Other... -> Git`
{% endhint %}

Now, you should see a window like this appear:

![](https://camo.githubusercontent.com/914f02d30059e58e584343bb47034f7dafdb7d25e810fc972193b002b39ee2d2/68747470733a2f2f692e696d6775722e636f6d2f41624233706d302e706e67)

If you copied the link from earlier, all the necessary fields should populate. Otherwise, enter all the text manually. When you're done click `Next >` and then `Finish`.

Great! You've got everything you need - you just can't see it yet. Right-click in the Package Explorer perspective, then select `Import...`. Under the `Maven` drop-down menu, select `Existing Maven Projects` then click `Next`. For the Root Directory, choose 'Browse' and \(on Windows\) navigate to `C:\Users\YourAccount\git` and select the `Quests` folder.

After Eclipse has finished importing, right-click the project name in the Package Explorer perspective and click `Properties`. In the left pane, select `Resource` and under `Text file encoding` select the `Other` bubble. Set the drop-down option to "UTF-8".

In the left pane, select `Java Build Path` and then the `Libraries` tab. Highlight `JRE System Library` and click the `Edit...` button. Ensure that the `Execution environment` is using JavaSE-1.8. If you don't see that option, you will need to [download JDK 8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) and restart Eclipse. Older versions of Java will not suffice. Select `Finish` once done, and you're good to go!

### Sharing edits

Once you've made the changes you desire, you're ready to either package it or upload it to your forked repository.

**To compile Quests into a jar** for use in a CraftBukkit/Spigot server, right-click the Quests project in the Package Explorer perspective and select `Run as -> Run Configurations`. In the Run Configurations window, select the `New launch configuration` button as shown below:

![](https://camo.githubusercontent.com/6bea529ca5b090c3b77d660e3c912a9c621deda65ee11bb7887761efd550080a/68747470733a2f2f692e696d6775722e636f6d2f6452734c5539672e706e67)

Name the configuration something familiar like "compile quests" and click `Browse Workspace...` to select "quests-parent". For `Goals:` simply type "clean package" _without_ the quotes. Finally, click `Run`. Any remaining dependencies will be downloaded and \(on Windows\) you will end up with a finished JAR file in `C:\Users\YourAccount\git\Quests\target`.

**To upload the changes** for future use in a Pull request, right-click the project in the Git Repositories perspective, and select `Commit...`. Drag any items in the Unstaged Changes window down into the Staged Changes window, then enter a brief description of the changes you made in the Commit Message window. Once you're completely sure you're ready to share your changes with the world, select the `Commit and Push...` button. No turning back now!

Visit your forked repository on Github and select the `New pull request` button to ask that the new commit\(s\) be merged into the master Quests repository. Follow the directions on-screen. Thank you for contributing to Quests!

