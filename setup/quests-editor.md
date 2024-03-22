# Éditeur de quête

Faisons des quête ! Par défaut l'éditeur de quête est disponible que pour les opérateurs du serveur. Cependant, avec les [bonnes permissions](https://pikamug.gitbook.io/quests/v/french-francais/configuration/commands-and-permissions) il est très simple pour certains staffs de faire la commande **/quests editor** en jeu (ou depuis la console, avec des fonctionnalités limitées). Vous serez accueilli par ce qui suit :

![](../.gitbook/assets/quest\_editor.png)

Entrez '1' dans le chat, et le plugin vous demandera un nom pour votre première quête. Il accepte aussi bien les lettres (majuscules ou miniscules) que les chiffres ainsi que les espaces. Mais en revanche les symboles et caractères spéciaux ne sont pas encore pris en compte. Si vous avez un doute sur le titre, il peut être changé plus tard.

Après avoir choisis un nom correct, cet écran apparaitra:

![](<../.gitbook/assets/quest\_main (1).png>)

<details>

<summary>Développez pour voir la ventilation.</summary>

1. Change the name of your quest
2. Shown to player when accepting quest
3. Shown to player after completing quest
4. Must speak to this Citizens or ZNPCsPlus NPC to start quest
5. Must right-click on this block to start quest
6. Must stand in this WorldGuard region to start quest
7. Use NPC GUI to start quest instead of chat
8. Change what a player needs to take your quest
9. Change the time(s) that your quest is available
10. Change what objectives your quest consists of
11. Change what a player gets for taking your quest
12. Change settings purely specific to your quest
13. Finish working on your quest
14. Discard all work on your quest

</details>

Il y vraiment beaucoup de choix ! Entrez '2' et indiquez un message au joueur qui souhaiterais prendre la quête. Validez, puis entrez '3' pour ajouter un message final qui récompensera le joueur.

{% hint style="info" %}
**Conseil de pro:** Si vous avez [Citizens 2](https://www.spigotmc.org/resources/citizens.13811/) ou [ZNPCsPlus](https://www.spigotmc.org/resources/znpcsplus.109380/) d'installé pour les PNJ, vous pouvez entrer '4' pour choisir le PNJ que vous souhaitez afin de lui confier votre quête.
{% endhint %}

Excellent travail ! Maintenant, si vous allez sauver votre quête, vous aurez une erreur. C'est parce que votre quête doit comporter au moins une étape, il faut donc la crée ! Entrez '11' pour commencer, puis '1' pour ajouter votre première étape.

![](../.gitbook/assets/quest\_stage.png)

<details>

<summary>Développez pour voir la ventilation.</summary>

1. Includes objectives to break, place, damage, or use blocks
2. Includes objectives to craft, smelt, enchant, brew or consume items
3. Includes objectives to deliver items to, talk to, or kill NPCs
4. Includes objectives to kill or tame mobs, catch fish, or shear sheep
5. Objective to kill an amount of players
6. Objective to travel to a specific radius of world coordinates
7. Objective to enter a specific string in chat
8. Objective from an installed [custom module](https://pikamug.gitbook.io/quests/v/french-francais/intermediaire/modules)
9. After setting at least one objective, run an [action](../casual/action-editor.md) at the start, end, or during the stage
10. After setting at least one objective, check a [condition](../expert/condition-editor.md) during the stage
11. Number of seconds to wait before the next stage may begin
12. After setting a delay, show a message to the player once the delay starts
13. Show a message to the player once the stage begins
14. Show a message to the player once the stage ends
15. Override the message shown to the player about what their objectives are
16. Permanently remove this stage
17. Finish working on your stage

</details>

Vive la magie des quêtes ! Il y a tellement d'objectifs différents que les possibilités sont presques sans fin ! Essayons de crée une quête basique, casser quelques blocs. Entrez '1' pour acceder au menu des blocs, puis encore '1' pour selectionner la destruction des blocs.

{% hint style="info" %}
**Conseil de pro:** Les objectifs customisés provienne d'add-on spéciaux qui sont en liens avec d'autres plugins que l'ont peut trouver [ici](https://pikamug.gitbook.io/quests/v/french-francais/intermediaire/modules). Pour en utiliser un, vous devrez l'installer dans le dossier /Quests/modules au démarrage.
{% endhint %}

![](../.gitbook/assets/quest\_break.png)

Ici, vous pouvez entrer quel bloc que vous souhaitez que le joueur casse. La terre est un défi facile, par exemple le joueur dois en casser 5. Si vous utiliser une version _supérieur_ à la 1.13, vous pouvez aussi définir une durabilité pour utiliser des variants (par exemple, la valeur '3' correspond à du pozdol plutôt qu'a de la terre).

{% hint style="info" %}
**Conseil de pro:** Les joueurs peuvent casser des blocs sans affecter la quête en utilisant une pioche avec l'enchantement toucher de soie, cette option peut être désactivé dans [Options](../beginner/options.md).
{% endhint %}

Entrez tous les numéros dans les menus pour « Terminé » jusqu'à ce que vous reveniez à l'écran de message 'demander/terminer'. Vous avez presque finis! Entrez '13' puis '1' pour enregistrer votre quête.

Bon travail ! Pour essayer votre nouvelle quête, **/questadmin reload** ou redémarrez le serveur (Ne _pas_ utiliser /reload) puis **/quests take \[votre nom de quête]**. Une fois que vous en aurez fait quelques autres, vous pouvez partager vos séries de quêtes les plus intéressantes ou en trouver d'autres sur [notre Discord](https://discord.com/invite/d56CQ6e). Bon jeu!
