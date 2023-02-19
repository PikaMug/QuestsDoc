# Éditeur de condition

{% hint style="info" %}
**Avertissement :** Ces informations sont destinées aux utilisateurs avancés. Procéder avec prudence!
{% endhint %}

Lorsqu'un joueur réalise une étape d'une quête, il peut être souhaitable de le forcer à répondre à certains critères. Par exemple, tenir un objet spécifique tout en remplissant des objectifs. Pour ce faire, une condition doit être créée et appliquée.

Pour créer une condition, lancez **/quests conditions** dans le jeu (ou depuis la console, avec des fonctionnalités limitées). Vous serez accueilli avec ce qui suit :

![](https://camo.githubusercontent.com/7c7cf8db7760543f731b49ec61ef1651886830e96b79c7ce4afb6741f53bb7dc/68747470733a2f2f692e696d6775722e636f6d2f6c7148626f4b492e706e67)

Entrez '1' dans le chat afin que le plugin puisse vous demander d'entrer un nom pour votre condition. Il peut s'agir de n'importe quelle séquence alphanumérique, ce qui signifie que les lettres et les chiffres sont acceptables, mais pas de caractères spéciaux ni de symboles ! Ne vous inquiétez pas, vous pourrez le modifier plus tard si vous n'êtes pas sûr.

Après avoir choisi un nom valide, cet écran apparaît :

![](https://camo.githubusercontent.com/23267d859c71ffcb3cd6f4123060c813a2d75817eb8c8a1f535f17c7f4fc2338/68747470733a2f2f692e696d6775722e636f6d2f455379363872492e706e67)

<details>

<summary>Développez pour voir la ventilation.</summary>

1. Change the name of your condition
2. Ride an entity or [Citizens](https://pikamug.gitbook.io/quests/v/french-francais/debutant/dependencies#citizens) NPC
3. Own permission, hold item in main hand, or wear items as armor
4. Stay within world, stay within ticks, stay within biome, or stay within WorldGuard region
5. Whether placeholder value is true
6. Whether to fail quest if condition not met
7. Finish working on your condition
8. Discard all work on your condition

</details>

Sélectionnez un type de condition et décidez si le joueur doit échouer à la quête si la condition souaitée n'est pas remplie. Maintenant, entrez tous les numéros d'invite appropriés pour "Terminé" jusqu'à ce que vous ayez enregistré votre condition.

Bon travail ! Contrairement à l'[éditeur de quête](../setup/quests-editor.md), il n'est pas nécessaire de recharger le plugin. Quittez l'éditeur de conditions, puis créez ou modifiez une quête dans l'éditeur de quête. Allez dans le menu "Modifier les étapes" et, après avoir défini au moins un objectif, sélectionnez l'option 11 pour appliquer la condition.
