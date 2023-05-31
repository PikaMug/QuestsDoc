# Configuration

Lors de la première éxecution de Quests, les fichiers de configuration sont automatiquement crées et sont localisé à l'adresse suivante /plugins/Quests. Si vous utilisez Quests pour la première fois, assurez-vous que les paramètres du fichier **config.yml** correspondent à vos attentes. Concernant les autres fichiers, ne vous en occupez pas tout de suite.

{% hint style="info" %}
**Conseil de pro:** Ouvrir un fichier .yml contenant des caractères non anglais sur un ordinateur anglais peut ne pas les affichés correctement. Pour le cas de windows, cela se produit car la langue anglaise utilise un jeu de caractère ANSI, tandis que le format préféré est UTF-8. Cela est difficile à modifier sur Windows, c'est pourquoi il est recommandé d'utiliser un programme qui supporte le format UTF-8, comme [Notepad++](https://notepad-plus-plus.org) qui est très populaire et gratuit.
{% endhint %}

### config.yml

Ce fichier contient tous les paramètres relatif au fonctionnement des quêtes une fois qu'elle sont chargées. C'est pour cela qu'il doit être configuré _avant_ le démarrage du serveur.

> [Ciquez ici pour voir la version par défaut config.yml](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/config.yml)

| Clé                                           | Type de données | Description                                                                                                                                                                             |
| --------------------------------------------- | --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| accept-timeout                                | nombre          | Combien (en secondes) de temps un joueur peut accepter ou refuser une quête avant que la console annule automatiquent                                                                   |
| allow-command-questing                        | true/false      | Permettre ou non aux joueurs d'accepter ou gérer une quête avec les commandes(e.g. /quests take SomeQuest).                                                                             |
| allow-command-quests-with-npcs                | true/false      | Permettre ou non aux joueurs d'accepter les quête par les PNJ (e.g. /quests take SomeQuest).                                                                                            |
| allow-pranks                                  | true/false      | Permettre ou non de cliquez sur un portail avec le journal de quête.                                                                                                                    |
| clickable-prompts                             | true/false      | Cliquez sur la plupart des sélections d'invites dans le chat.                                                                                                                           |
| condition-interval                            | nombre          | Combien (en secondes) de temps entre les notifications d'état (min. 3, max. 180).                                                                                                       |
| confirm-abandon                               | true/false      | Si les joueurs doivent ou non confirmer l'abandon d'une quête.                                                                                                                          |
| confirm-accept                                | true/false      | Si les joueurs doivent ou non confirmer la prise d'une quête.                                                                                                                           |
| console-logging                               | nombre          | 0 = désactivé, 1 = édition de l'histoire, 2 = et démarrage/arêt des quêtes, 3 = et récompense, 4 = et les informations de débuggage.                                                    |
| disable-command-feedback                      | true/false      | Désactiver ou non la règle de jeu sendCommandFeedback de Minecraft au démarrage.                                                                                                        |
| generate-files-on-join                        | true/false      | Défnir quand générer un fichier de données de joueur, soit lorsque ce joueur rejoint le serveur pour la première fois ou uniquement lorsqu'il utilise les quêtes pour la première fois. |
| give-journal-item                             | true/false      | Journal de Quête existe en tant qu'objet dans l'inventaire du joueur.                                                                                                                   |
| ignore-locked-quests                          | true/false      | Ignorer les quêtes verrouillées lors de la vérification joueur a toutes les exigences nécessaires.                                                                                      |
| kill-delay                                    | nombre          | Combien (en secondes) de temps un joueur doit attendre après avoir tué un joueur pour une quête avant de pouvoir tuer à nouveau ce joueur.                                              |
| language                                      | string          | Quel fichier du dossier /lang/ sera utilisé pour le texte administratif. Par exemple, une valeur de "FR-fr" entraînera le chargement de "/lang/FR-fr/strings.yml".                      |
| language-override-client                      | true/false      | Indique si le paramètre de `language` doit remplacer la langue du client lors de l'envoi de texte.                                                                                      |
| max-quests                                    | nombre          | Nombre maximum de quête que le joueur peut avoir en même temps.                                                                                                                         |
| npc-effects.enabled                           | true/false      | Activer ou non les effets de particules. Notez que le client (joueur) doit avoir des particules activées.                                                                               |
| npc-effects.new-quest                         | string          | L'effet de particule à jouer pour une nouvelle quête (ex. note, enchantement, critique, sort,...).                                                                                      |
| npc-effects.redo-quest                        | string          | L'effet de particule à jouer pour une quête répétable (ex. note, enchantement, critique, sort,...).                                                                                     |
| show-requirements                             | true/false      | Permettre aux joueurs de voir les exigences dans /quest \[quête]                                                                                                                        |
| show-titles                                   | true/false      | Afficher les titres aux joueurs lors de l'acceptation/l'achèvement des quêtes.                                                                                                          |
| strict-player-movement                        | nombre          | Secondes entre le suivi avancé des mouvements des joueurs.                                                                                                                              |
| storage-data.address                          | string          | L'adresse IP pour le stockage facultatif.                                                                                                                                               |
| storage-data.database                         | string          | Le nom de la table pour le stockage facultatif.                                                                                                                                         |
| storage-data.username                         | string          | Le mot de passe de connexion pour le stockage facultatif.                                                                                                                               |
| storage-data.password                         | string          | Le mot de passe de connexion pour le stockage facultatif.                                                                                                                               |
| storage-data.pool-settings.max-pool-size      | nombre          | Paramètre HikariCP avancé.                                                                                                                                                              |
| storage-data.pool-settings.min-idle           | nombre          | Paramètre HikariCP avancé.                                                                                                                                                              |
| storage-data.pool-settings.max-lifetime       | nombre          | Paramètre HikariCP avancé.                                                                                                                                                              |
| storage-data.pool-settings.connection-timeout | nombre          | Paramètre HikariCP avancé.                                                                                                                                                              |
| storage-method.player-data                    | string          | yaml = stockage de fichiers, mysql = stockage à distance, custom = stockage développeur                                                                                                 |
| top-limit                                     | nombre          | Nombre maximum de quêtes pouvant être affichées par /quests top \[nombre]                                                                                                               |
| translate-names                               | true/false      | Traduisez le nom de l'élément dans la langue du jeu du client.                                                                                                                          |
| translate-subcommands                         | true/false      | Traduire les sous-commandes dans la langue du plugin du serveur.                                                                                                                        |
| trial-save                                    | true/false      | Autoriser l'enregistrement en Mode D'essai.                                                                                                                                             |
| update-check                                  | true/false      | Indique s'il faut autoriser la vérification des mises à jour du plug-in.                                                                                                                |

### actions.yml

{% hint style="info" %}
La modification manuelle de ce fichier n'est pas conseillée. Aucune assistance ne sera apportée à ceux qui choisissent de ne pas utiliser l'éditeur en jeu.
{% endhint %}

Ce fichier contient des actions personnalisées qui exécutent certaines tâches et effets. À l'exception des exemples inclus, les actions sont créées avant d'être utilisées dans une quête. Ceci est mieux accompli avec la commande _/quests actions_.

> [Cliquez ici pour voir le fichier par défaut actions.yml](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/actions.yml)

### conditions.yml

{% hint style="info" %}
La modification manuelle de ce fichier n'est pas conseillée. Aucune assistance ne sera apportée à ceux qui choisissent de ne pas utiliser l'éditeur en jeu.
{% endhint %}

Ce fichier contient des conditions personnalisées qui sont vérifiées pendant le jeu. À l'exception des exemples inclus, les conditions sont créées avant l'utilisation dans une quête. Ceci est mieux accompli avec la commande _/quests conditions_.

> [Cliquez ici pour voir le fichier par défaut conditions.yml](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/conditions.yml)

### quests.yml

{% hint style="info" %}
La modification manuelle de ce fichier n'est pas conseillée. Aucune assistance ne sera apportée à ceux qui choisissent de ne pas utiliser l'éditeur en jeu.
{% endhint %}

Ce fichier contient toutes les quêtes enregistrées. Quelques exemples de quêtes sont inclus que vous pouvez supprimer à tout moment. Ceci est mieux accompli avec la commande _/quests editor_.

> [Cliquez ici pour voir le fichier par défaut quests.yml](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/quests.yml)
