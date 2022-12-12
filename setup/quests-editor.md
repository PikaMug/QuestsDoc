# Éditeur de quête

Faisons des quête ! Par défaut l'éditeur de quête est disponible que pour les opérateurs du serveur. Cependant, avec les [bonnes permissions](https://pikamug.gitbook.io/quests/v/french-francais/configuration/commands-and-permissions) il est très simple pour certains staffs de faire la commande **/quests editor** en jeu (ou depuis la console, avec des fonctionnalités limitées). Vous serez accueilli par ce qui suit :

![](https://camo.githubusercontent.com/fd0571c9f8dd71b0cdcd37522e00efd6841fb861d9c74cc0f0936b5688ba6f39/68747470733a2f2f692e696d6775722e636f6d2f35664c645170612e706e67)

Entrez '1' dans le chat, et le plugin vous demandera un nom pour votre première quête. Il accepte aussi bien les lettres (majuscules ou miniscules) que les chiffres ainsi que les espaces. Mais en revanche les symboles et caractères spéciaux ne sont pas encore pris en compte. Si vous avez un doute sur le titre, il peut être changé plus tard.

Après avoir choisis un nom correct, cet écran apparaitra:

![](https://camo.githubusercontent.com/fda7a8693ba61b3a030bccc4911a806db2346282c26833a2d3d9195be39f2641/68747470733a2f2f692e696d6775722e636f6d2f4865473977394b2e706e67)

Comme vous pouvez le voir, il y vraiment beaucoup de choix, entrez '2' et indiquez un message au joueur qui souhaiterais prendre la quête. Validez, puis entrez '3' pour ajouter un message final qui récompensera le joueur.

{% hint style="info" %}
**Conseil de pro:** Si vous avez [Citizens 2](https://www.spigotmc.org/resources/citizens.13811/) d'installé pour les PNJ, vous pouvez entrer '4' pour choisir le PNJ que vous souhaitez afin de lui confier votre quête.
{% endhint %}

Félicitation, si vous sauvegardé votre quête maintenant, vous aurez une erreur. C'est parce que votre quête doit comporter au moins une étape, il faut donc la crée ! Entrez '11' pour commencer, puis '1' pour ajouter votre première étape.

![](https://camo.githubusercontent.com/9065d04debad1a0a95a37fc3baa6518478dd7d4989d3abd63773f7b8c6a385ea/68747470733a2f2f692e696d6775722e636f6d2f61556562344a512e706e67)

Vive la magie des quêtes ! Il y a tellement d'objectifs différents que les possibilités sont presques sans fin ! Essayons de crée une quête basique, casser quelques blocs. Entrez '1' pour acceder au menu des blocs, puis encore '1' pour selectionner la destruction des blocs.

{% hint style="info" %}
**Conseil de pro:** Les objectifs customisés provienne d'add-on spéciaux qui sont en liens avec d'autres plugins que l'ont peut trouver [ici](https://pikamug.gitbook.io/quests/v/french-francais/intermediaire/modules). Pour en utiliser un, vous devrez l'installer dans le dossier /Quests/modules au démarrage.
{% endhint %}

![](https://camo.githubusercontent.com/e30adfdd454a751bb6ac89e116223d44731c9ecb7939bbe0438de6ecbb2da2c4/68747470733a2f2f692e696d6775722e636f6d2f393267764744492e706e67)

Ici, vous pouvez entrer quel bloc que vous souhaitez que le joueur casse. La terre est un défi facile, par exemple le joueur dois en casser 5. Si vous utiliser une version _supérieur_ à la 1.13, vous pouvez aussi définir une durabilité pour utiliser des variants (par exemple, la valeur '3' correspond à du pozdol plutôt qu'a de la terre).

{% hint style="info" %}
**Conseil de pro:** Les joueurs peuvent casser des blocs sans affecter la quête en utilisant une pioche avec l'enchantement toucher de soie, cette option peut être désactivé dans [Options](../beginner/options.md).
{% endhint %}

Entrez tous les numéros dans les menus pour « Terminé » jusqu'à ce que vous reveniez à l'écran de message 'demander/terminer'. Vous avez presque finis! Entrez '13' puis '1' pour enregistrer votre quête.

Bon travail ! Pour essayer votre nouvelle quête, **/questadmin reload** ou redémarrez le serveur (Ne _pas_ utiliser /reload) puis **/quests take \[votre nom de quête]**. Une fois que vous en aurez fait quelques autres, vous pouvez partager vos séries de quêtes les plus intéressantes ou en trouver d'autres sur [notre Discord](https://discord.com/invite/d56CQ6e). Bon jeu!
