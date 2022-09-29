# Commandes & Permissions

Les 3 commandes principales sont: **/quests**, **/quest**, et **/questadmin**. Les deux premières sont utilisables par tous les joueurs par défaut, cependant la dernière est réservé pour les opérateurs du serveur. Pour changer ceci, comme donner la permission **/questadmin** aux administrateurs non-op,  vous devrez le configurer avec ces [permissions](https://bukkit.gamepedia.com/Understanding\_Permissions).

### Commandes de joueurs

Vous trouverez ci-dessous un tableau décrivant chaque commande et son autorisation associée. Notez que les sous-commandes (list, take, quit, ...) peuvent êtres changées si vous [changez la langue du plugin](https://github.com/PikaMug/Quests/wiki/Translations), mais les permissions restent les mêmes.

| Commandes             | Permissions      | Description                            |
| --------------------- | ---------------- | -------------------------------------- |
| /quests               | quests.quests    | Affiche l'aide du plugin               |
| /quests list \[page]  | quests.list      | Liste des quêtes disponibles           |
| /quests take \[quest] | quests.take      | Prendre une quête avec les commandes   |
| /quests quit \[quest] | quests.quit      | Quitter une quête active               |
| /quests stats         | quests.stats     | Voir les statistiques des quêtes       |
| /quests top \[nombre] | quests.top       | Voir le classement                     |
| /quests info          | quests.info      | Voir les informations du plugin        |
| /quests journal       | quests.journal   | Obtenir/retirer le journal de quête    |
| N/A                   | quests.compass   | Chercher les quêtes avec une boussole  |
|                       |                  |                                        |
| /quest                | quests.quest     | Voir les objectifs des quêtes actives  |
| /quest \[quest]       | quests.questinfo | Voir les information sur une quête     |

{% hint style="info" %}
**Astuce de pro:** Par défault, vous pouvez aussi utiliser **/qs** et **/q** au lieu de **/quests** et **/quest**, respectivement!
{% endhint %}

### Commandes administrateurs

Les commandes d'administrateurs, qui doivent être accordées qu'à ceux en qui vous avez confiance, et pour ne pas qu'ils en abusent, sont décrites ci-dessous.

| Commandes                                        | Permissions              | Description                                         |
| ------------------------------------------------ | ------------------------ | --------------------------------------------------- |
| /questadmin                                      | quests.admin             | Affiche l'aide administrateur                       |
| /questadmin stats \[joueur]                      | quests.admin.stats       | Affiche les stats d'un joueur                       |
| /questadmin give \[joueur] \[quête]              | quests.admin.give        | Force un joueur à prendre une quête (ignore les prérequis)                 |
| /questadmin quit \[joueur] \[quête]              | quests.admin.quit        | Force un joueur à quitter une quête                 |
| /questadmin points \[joueur] \[quête]            | quests.admin.points      | Définis un nombre de point de quête à un joueur     |
| /questadmin takepoints \[joueur] \[quantité]     | quests.admin.takepoints  | Retire des points de quête d'un joueur              |
| /questadmin givepoints \[joueur] \[quantité]     | quests.admin.givepoints  | Ajoute des points de quête à un joueur              |
| /questadmin pointsall \[quantité]                | quests.admin.pointsall   | Définis un nombre de point de quête à tous les joueurs              |
| /questadmin finish \[joueur] \[quête]            | quests.admin.finish      | Force un joueur à terminer une quête (ignore les objectifs)             |
| /questadmin nextstage \[joueur] \[quête]         | quests.admin.nextstage   | Force un joueur à terminer l'étape actuelle          |
| /questadmin setstage \[joueur] \[quête] \[étape] | quests.admin.setstage    | Impose une étape pour un joueur                      |
| /questadmin reset \[joueur]                      | quests.admin.reset       | Supprime tout les données de quête d'un joueur       |
| /questadmin remove \[joueur] \[quête]            | quests.admin.remove      | Supprime une quête terminé d'un joueur               |
| /questadmin reload                               | quests.admin.reload      | Recharge sans risque le plugin                       |
| N/A                                              | quests.admin.drop        | Donne la possibilité de drop son journal de quête    |
| N/A                                              | quests.admin.update      | Voir les information de mise à jour du plugin                    |
| N/A                                              | quests.mode.trial        | Accès limitée aux éditeurs, désactivé par défaut      |
| /quests editor                                   | quests.editor.editor     | Permission d'ouvrir l'éditeur de quête               |
| N/A                                              | quests.editor.create     | Permission de crée de nouvelles quêtes               |
| N/A                                              | quests.editor.edit       | Permission d'éditer les quêtes éxistantes            |
| N/A                                              | quests.editor.delete     | Permission de supprimer des quêtes                   |
| /quests actions                                  | quests.actions.editor    | Permission d'ouvrir l'éditeur d'actions              |
| N/A                                              | quests.actions.create    | Permission de crée de nouvelles actions              |
| N/A                                              | quests.actions.edit      | Permission d'éditer les actions existantes           |
| N/A                                              | quests.actions.delete    | Permission de supprimer des actions                  |
| /quests conditions                               | quests.conditions.editor | Permission d'ouvrir l'éditeur de conditions          |
| N/A                                              | quests.conditions.create | Permission de crée de nouvelles conditions           |
| N/A                                              | quests.conditions.edit   | Permission d'éditer les conditions existantes            |
| N/A                                              | quests.conditions.delete | Permission de supprimer des conditions               |

{% hint style="info" %}
**Astuce de pro:** Pour englober respectivement toutes les autorisations d'administrateur et d'éditeur vous pouvez utiliser _quests.admin.\*_, _quests.editor.\*_, _quests.actions.\*_ et _quests.conditions.\*_ ! Par défaut, vous pouvez utilisé **/qa** en remplacement de **/questadmin**!
{% endhint %}
