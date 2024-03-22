# Stockage

Vous pouvez choisir de modifier votre option de stockage via le paramètre `storage-method` du [fichier de configuration Quests](https://pikamug.gitbook.io/quests/v/french-francais/configuration/configuration). Les choix disponibles sont décrits ci-dessous. Si vous souhaitez changer votre méthode de stockage plus tard sans perdre de données, utilisez d'abord [QuestsConverter](https://github.com/PikaMug/QuestsConverter).

### YAML

Il s'agit de la sélection par défaut qui enregistrera les données du joueur dans des fichiers .yml séparés sous le dossier _/Quests/data_. Il est recommandé pour les utilisateurs débutants et occasionnels car il fonctionne "prêt à l'emploi" sans aucune configuration supplémentaire requise.

### MySQL

Cela enregistrera les données du joueur dans une base de données MySQL locale ou distante que vous avez configurée à l'avance. Les paramètres de table et de connexion peuvent être spécifiés via les paramètres `storage-data`. Un exemple d'une telle configuration pourrait ressembler à :

```
storage-data:
  address: localhost
  database: minecraft
  username: root
  password: MonMoTdePaSScompleXe
  table_prefix: quests_
  pool-settings:
    max-pool-size: 10
    min-idle: 10
    max-lifetime: 1800000
    connection-timeout: 5000
```

Notez que HikariCP a été shaded en interne pour maximiser la vitesse de connexion sur les serveurs très peuplés.

### Customisé

Un développeur peut choisir d'utiliser une option de stockage personnalisée. Voir [ici](https://github.com/PikaMug/Quests/tree/main/api/src/main/java/me/pikamug/quests/storage/implementation/custom).
