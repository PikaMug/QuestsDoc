# Éditeur de action

Semblable à la façon dont toutes les étapes de quête ont des objectifs, elles peuvent également effectuer des actions. Une action est quelque chose qui se produit pendant une étape, mais qui est généralement cosmétique et ne fait pas progresser la quête. Par exemple, faire perdre la faim à un joueur ou être frappé par la foudre sont considérés comme des actions.

Pour effectuer une action, lancez **/quests actions** dans le jeu (ou depuis la console, avec des fonctionnalités limitées). Vous serez accueilli avec ce qui suit :

![](../.gitbook/assets/action\_editor.png)

Entrez '1' dans le chat pour que le plugin puisse vous demander d'entrer un nom pour votre action. Il peut s'agir de n'importe quelle séquence alphanumérique, ce qui signifie que les lettres et les chiffres sont acceptables, mais pas de caractères spéciaux ni de symboles ! Ne vous inquiétez pas, vous pourrez le modifier plus tard si vous n'êtes pas sûr.

Après avoir choisi un nom valide, cet écran apparaît :

![](../.gitbook/assets/action\_main.png)

<details>

<summary>Développez pour voir la ventilation.</summary>

1. Change the name of your action
2. Send message, clear inventory, give items, apply potion effects, set hunger level, set saturation level, teleport to location, or execute commands
3. Set time to fail quest and whether to cancel the quest timer
4. Set effects or set explosion locations
5. Set storm or thunder in a particular world, or set lightning strike locations
6. Action to spawn mobs
7. Run a [Denizen](https://pikamug.gitbook.io/quests/v/french-francais/debutant/dependencies#denizen) script
8. Action to fail the quest
9. Finish working on your action
10. Discard all work on your action

</details>

Pour l'instant, entrez '5' pour le menu Météo, puis '2' pour configurer une action qui forcera le tonnerre sur un monde pendant un certain temps.

![](../.gitbook/assets/action\_thunder.png)

Entrez '1' pour sélectionner l'un des mondes de votre serveur Minecraft par son nom. Ils seront répertoriés pour votre commodité, mais vous ne pouvez en sélectionner qu'un ! Vous pouvez créer une deuxième action plus tard si vous souhaitez distribuer le tonnerre sur plusieurs mondes.

Une fois cela fait, entrez '2' pour définir une durée en secondes. C'est la durée de l'événement tonnerre. Par exemple, tapez 180 pour que l'événement dure 3 minutes. Maintenant, entrez tous les numéros d'invite appropriés pour "Terminé" jusqu'à ce que vous ayez enregistré votre action.

Bon travail ! Contrairement à l'[éditeur de quete](../setup/quests-editor.md), il n'est pas nécessaire de recharger le plugin. Quittez l'éditeur d'action, puis créez ou modifiez une quête dans l'éditeur de quête. Allez dans le menu "Modifier les étapes" et, après avoir défini au moins un objectif, sélectionnez l'option 9 pour exécuter l'action avant, pendant ou après l'étape :

![](../.gitbook/assets/action\_quest.png)

<details>

<summary>Développez pour voir la ventilation.</summary>

1. Activate on start of stage
2. Activate at end of stage
3. Activate if player fails quest
4. Activate if player dies during stage
5. Activate if player disconnects during stage
6. Activate if chat message sent during stage
7. Activate if command run during stage
8. Save and return to previous menu

</details>

Les actions de chats et de commandes sont exécutées pendant l'étape lorsque le joueur entre un mot-clé ou une commande spécifique dans le jeu, respectivement.
