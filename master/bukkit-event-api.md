# Bukkit Event API

{% hint style="info" %}
**Alert:** This information is intended for developers. Learn how to use Java first!
{% endhint %}

### Add to your project

If you're using Maven or another project management tool, add the latest version of Quests through the CodeMC service.

```xml
<repository>
  <id>codemc-repo</id>
  <url>https://repo.codemc.io/repository/maven-public/</url>
</repository>
```

Unless designing a cross-platform project, you'll want to define the core artifact.

```xml
<dependency>
  <groupId>me.blackvein.quests</groupId>
  <artifactId>quests-core</artifactId>
  <version>VERSION</version>
</dependency>
```

### Learn the interface

Starting with Quests 3.7.0, a Bukkit-style Event API is available. If you do not see an Event you would like, please [submit a Pull Request](https://github.com/PikaMug/Quests/pulls). All other inquiries for a new Event to be added will be ignored.

[Click here to see available Events](https://github.com/PikaMug/Quests/tree/main/api/src/main/java/me/blackvein/quests/events)
