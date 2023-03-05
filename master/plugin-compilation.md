# Compilation du plugin

{% hint style="info" %}
**ALERTE:** Ces informations sont destinées aux développeurs. Apprenez d'abord à utiliser Java !
{% endhint %}

### Configurer un IDE

Si vous voulez [contribuer](https://github.com/PikaMug/Quests/pulls) sans l'utilisation des outils en ligne de Github, ou si vous souhaitez simplement modifier certains aspects du plugin pour vous-même, la meilleure façon de le faire est de compiler le plugin localement sur votre propre machine.

Bien que cela puisse être accompli à l'aide plusieurs programmes, nous recommandons [IntelliJ IDEA](https://www.jetbrains.com/idea/). Une compréhension de base d'Apache Maven est suggérée.

### Télécharger le code source

Avec votre machine prête à fonctionner, téléchargeons la source des quêtes. Si vous avez l'intention de soumettre une demande d'extraction, nous vous recommandons [création d'un fork](https://guides.github.com/activities/forking/) afin que vous puissiez demander que vos modifications soient fusionnées dans ce référentiel. Sinon, si vous souhaitez uniquement compiler localement avec vos propres modifications, copiez ce lien :

`https://github.com/PikaMug/Quests.git`

Ouvrez IntelliJ. Si vous êtes actuellement dans un projet, allez dans `File -> Close Project`. Sur l'écran Bienvenue dans IntelliJ IDEA, cliquez sur le bouton Get from VCS. Collez l'URL ci-dessus et cliquez sur Clone. Donnez au projet un peu de temps pour se charger, puis explorez la Project persepctive dans la barre des tâches de gauche.

### Partage des modifications

Une fois que vous avez apporté les modifications souhaitées, vous êtes prêt à le packager ou à le télécharger dans votre référentiel forké.

**Pour compiler les quêtes dans un fichier jar** ou les utiliser dans un serveur Spigot/Paper, ouvrez la Maven perspective dans la barre des tâches de droite et développez `quests (root)`. Sélectionnez l'option `package`. Toutes les dépendances restantes seront téléchargées et (sous Windows) vous vous retrouverez avec un fichier JAR fini dans`C:\Users\YourAccount\IdeaProjects\Quests\dist\target`.

**Pour télécharger les modifications** pour une utilisation future dans une demande d'extraction, ouvrez la Commit perspective dans la barre des tâches de gauche. Assurez-vous que tous les fichiers que vous souhaitez transmettre sont cochés, puis donnez une courte description à votre commit. Une fois que vous êtes complètement sûr que vous êtes prêt à partager vos modifications avec le monde, sélectionnez le bouton "Commit and Push..." et suivez les invites.

Visitez votre référentiel forké sur Github et sélectionnez le bouton `New pull request` pour demander que le(s) nouveau commit(s) soit fusionné dans le référentiel principal des quêtes. Suivez les instructions à l'écran. Merci de contribuer aux quêtes !
