# Plugin Compilation

{% hint style="info" %}
**Alert:** This information is intended for developers. Learn how to use Java first!
{% endhint %}

### Set up an IDE

If you would like to [contribute a Pull Request](https://github.com/PikaMug/Quests/pulls) without the use of Github's online tools, or would just like to change some aspects of the plugin for yourself, the best way to do so is to compile the plugin locally on your own machine.

Although this can be accomplished in several programs, we recommend [IntelliJ IDEA](https://www.jetbrains.com/idea/). A basic understanding of Apache Maven is suggested.

### Download the source code

With your machine raring to go, let's download the Quests source. If you intend on submitting a Pull Request, we recommend [creating a fork](https://guides.github.com/activities/forking/) so that you can request that your changes be merged into this repository. Otherwise, if you only want to compile locally with your own edits, copy this link:

`git@github.com:PikaMug/Quests.git`

Open IntelliJ. If you are currently in a project, go to `File -> Close Project`. At the Welcome to IntelliJ IDEA screen, click the Get from VCS button. Paste the URL from above and click Clone. Give the project some time to load, then explore the Project persepctive in the left taskbar.

### Sharing edits

Once you've made the changes you desire, you're ready to either package it or upload it to your forked repository.

**To compile Quests into a jar** for use in a Spigot/Paper server, open the Maven perspective in the right taskbar and expand `quests (root)`. Select the `package` option. Any remaining dependencies will be downloaded and \(on Windows\) you will end up with a finished JAR file in `C:\Users\YourAccount\IdeaProjects\Quests\dist\target`.

**To upload the changes** for future use in a Pull Request, open the Commit perspective in the left taskbar. Make sure all files you wish to trasmit are checked, then give your commit a short description. Once you're completely sure you're ready to share your changes with the world, select the `Commit and Push...` button and follow the prompts.

Visit your forked repository on Github and select the `New pull request` button to ask that the new commit\(s\) be merged into the master Quests repository. Follow the directions on-screen. Thank you for contributing to Quests!

