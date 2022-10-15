# Storage

{% hint style="info" %}
**Warning:** This information is intended for advanced users. Proceed with caution!
{% endhint %}

As of Quests 4.0.0-rc.3, you may elect to change your storage option through the `storage-method` setting of [the Quests configuration file](https://pikamug.gitbook.io/quests/setup/configuration#config.yml). The available choices are described below. If you should wish to change your storage method later without losing data, first use [QuestsConverter](https://github.com/PikaMug/QuestsConverter).

### YAML

This is the default selection which will save player data to separated .yml files under the _/Quests/data_ folder. It is recommended for beginner and casual users as it works right "out of the box" with no additional setup required.

### MySQL

This will save player data to a local or remote MySQL database that you have configured ahead of time. Table and login settings may be specified via the `storage-data` settings. An example of such configuration might look like:

```
storage-data:
  address: localhost
  database: minecraft
  username: root
  password: myComplexPassword
  table_prefix: quests_
  pool-settings:
    max-pool-size: 10
    min-idle: 10
    max-lifetime: 1800000
    connection-timeout: 5000
```

Note that HikariCP has been shaded internally to maximize connection speed on largely-populated servers.

### Custom

A developer may opt to employ a custom storage option. See [here](https://github.com/PikaMug/Quests/tree/main/core/src/main/java/me/blackvein/quests/storage/implementation/custom).
