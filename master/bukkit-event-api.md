# Bukkit Event API

{% hint style="info" %}
**Тревога:** Тази информация е предназначена за разработчици. Научете първо как да използвате Java!
{% endhint %}

### Добавете към вашия проект

Ако използвате Maven или друг инструмент за управление на проекти, добавете най-новата версия на Quests чрез услугата CodeMC.

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

Започвайки с Quests 3.7.0, е наличен API за събития в стил Bukkit. Ако не виждате Event, което искате, моля [submit a Pull Request](https://github.com/PikaMug/Quests/pulls). Всички други запитвания за добавяне на нов Event ще бъдат игнорирани.

[Щракнете тук, за да видите наличните Events](https://github.com/PikaMug/Quests/tree/main/api/src/main/java/me/blackvein/quests/events)

