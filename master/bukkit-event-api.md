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
```xml
<dependency>
  <groupId>me.blackvein.quests</groupId>
  <artifactId>quests-api</artifactId>
  <version>VERSION</version>
</dependency>
```

You may also need the core module.

```xml
<dependency>
  <groupId>me.blackvein.quests</groupId>
  <artifactId>quests-core</artifactId>
  <version>VERSION</version>
</dependency>
```

### Learn the interface

Starting with Quests 3.7.0, a Bukkit-style Event API is available. If you do not see an Event you would like added, please [submit a Pull Request](https://github.com/PikaMug/Quests/pulls). Requests for new events to be added will be ignored.

[Click here to see available Events](https://github.com/PikaMug/Quests/tree/master/main/src/main/java/me/blackvein/quests/events)

