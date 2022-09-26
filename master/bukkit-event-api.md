# Evenements Bukkit API

{% hint style="info" %}
ALERTE: Ces informations sont destinées aux développeurs. Apprenez d'abord à utiliser Java !
{% endhint %}

### Ajouter à votre projet

Si vous utilisez Maven ou un autre outil de gestion de projet, ajoutez la dernière version de Quests via le service CodeMC.

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

Vous pouvez également avoir besoin du module de base.

```xml
<dependency>
  <groupId>me.blackvein.quests</groupId>
  <artifactId>quests-core</artifactId>
  <version>VERSION</version>
</dependency>
```

### Apprendre l'interface

À partir de Quests 3.7.0, une API d'événement de style Bukkit est disponible. Si vous ne voyez pas un événement que vous aimeriez, veuillez [soumettre une demande d'extraction](https://github.com/PikaMug/Quests/pulls).Toutes les autres demandes d'ajout d'un nouvel événement seront ignorées.

[Cliquez ici pour voir les événements disponibles](https://github.com/PikaMug/Quests/tree/master/main/src/main/java/me/blackvein/quests/events)

