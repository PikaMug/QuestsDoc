# Modules

{% hint style="info" %}
**Remarque:** Ces informations sont destinées aux utilisateurs intermédiaires. Lire attentivement!
{% endhint %}

Les plugins qui s'intègrent aux quêtes pour fournir des objectifs, des récompenses et des exigences personnalisés utilisent ce que l'on appelle des _modules_. Un module est un fichier jar créé par les développeurs à l'aide de [Quests API](https://pikamug.gitbook.io/quests/v/french-francais/maitre/custom-quest-api), qui agit comme un intermédiaire entre les invités et le plugin d'intégration. Ceci est en contraste avec les [dépendances](https://pikamug.gitbook.io/quests/v/french-francais/debutant/dependencies), pour lequel vous n'avez généralement pas besoin d'un module.

Les jars de module doivent être placés dans le dossier _Quests/modules_, tandis que le plugin cible va dans le dossier _/plugins_ comme d'habitude. Notez que tous les modules sont entièrement facultatifs et que vous pouvez les ajouter ou les supprimer comme bon vous semble. Vous trouverez ci-dessous une liste incomplète des plugins populaires pour lesquels un module est connu, ainsi qu'une description de la façon dont il est lié.

| Légende:                                                 |                                                      |
| -------------------------------------------------------- | ---------------------------------------------------- |
| 🌟 = Recommandé pour une expérience utilisateur optimale | 💲 = Peut nécessiter l'achat d'une ressource premium |

<table data-view="cards"><thead><tr><th align="center"></th><th></th><th align="center"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td align="center"><strong>BedWars1058</strong> 💲</td><td><em>Adds "Start arena", "Open shop", "Buy item", "Buy upgrade", "Destroy bed", "Kill player", and "End arena" objectives.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/38-bedwars1058-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/bedwars1058-quests-module.100722/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_bedwars1058.png">icon_bedwars1058.png</a></td></tr><tr><td align="center"><strong>Boss</strong> 💲</td><td><em>Adds a "Kill Boss" objective.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/8-boss-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/boss-quests-module.66973/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_boss.png">icon_boss.png</a></td></tr><tr><td align="center"><strong>CustomMobs</strong></td><td><em>Adds a "Kill CustomMobs" objective.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/41-custommobs-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/custommobs-quests-module.56686/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_custommobs.png">icon_custommobs.png</a></td></tr><tr><td align="center"><strong>DungeonsXL</strong></td><td><em>Adds "Finish dungeon", "Get reward item", "Get reward level", "Get reward money", and "Kill dungeon mob" objectives.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/7-dungeonsxl-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/dungeonsxl-quests-module.66703/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_dungeonsxl.png">icon_dungeonsxl.png</a></td></tr><tr><td align="center"><strong>Interactions</strong> 💲</td><td><em>Adds "Start conversation" and "End conversation" objectives.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/3-interactions-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/interactions-quests-module.92421/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_interactions.png">icon_interactions.png</a></td></tr><tr><td align="center"><strong>Magic</strong></td><td><em>[Outdated] Link with various Magic spells and tasks.</em></td><td align="center"><a href="http://jenkins.elmakers.com/job/MagicQuests/">Elmakers</a></td><td><a href="../.gitbook/assets/icon_magic.png">icon_magic.png</a></td></tr><tr><td align="center"><strong>Marcely's Bedwars</strong> 💲</td><td><em>Adds "Start arena", "Open shop", "Buy item", "Buy upgrade", "Destroy bed", "Kill player", and "End arena" objectives.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/46-marcely&#x27;s-bedwars-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/marcelys-bedwars-quests-module.107857/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_marcelys_bedwars.png">icon_marcelys_bedwars.png</a></td></tr><tr><td align="center"><strong>mcMMO Overhaul</strong> 💲</td><td><em>Adds "Skill" reward and requirement. Not for use with mcMMO Classic.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/2-mcmmo-overhaul-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/92962/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_mcmmo_overhaul.png">icon_mcmmo_overhaul.png</a></td></tr><tr><td align="center"><strong>MMOItems</strong> 💲</td><td><em>Adds "Deliver MMO item" objective, "MMO item" requirement, and "MMO item" reward.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/49-mmoitems-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/mmoitems-quests-module.115654/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_mmoitems.png">icon_mmoitems.png</a></td></tr><tr><td align="center"><strong>MobArena</strong></td><td><em>Adds "Kill mobs", "Finish wave", and "Complete arena" objectives.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/6-mobarena-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/mobarena-quests-module.72355/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_mobarena.png">icon_mobarena.png</a></td></tr><tr><td align="center"><strong>MythicMobs</strong> 🌟💲</td><td><em>Adds "Deliver mythic item and "Kill mythic mob" objectives, "mythic item" requirement, and "mythic item" and "spawn mythic mob" rewards.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/48-mythicmobs-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/113916/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_mythicmobs.png">icon_mythicmobs.png</a></td></tr><tr><td align="center"><strong>NPCDestinations</strong></td><td><em>Adds NPC location requirements and reward.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/40-npcdestinations-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/101588/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_npcdestinations.png">icon_npcdestinations.png</a></td></tr><tr><td align="center"><strong>PhatLoots</strong></td><td><em>Adds loot reward and objective.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/43-phatloots-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/phatloots-quests-module.102525/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_phatloots.png">icon_phatloots.png</a></td></tr><tr><td align="center"><strong>Proskillapi</strong></td><td><em>Adds class requirements and rewards. Module is auto-installed by Proskillapi!</em></td><td align="center"><a href="https://www.spigotmc.org/resources/91913/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_proskillapi.png">icon_proskillapi.png</a></td></tr><tr><td align="center"><strong>Screaming BedWars</strong> 💲</td><td><em>Adds "Start arena", "Open shop", "Buy item", "Buy upgrade", "Destroy bed", "Kill player", and "End arena" objectives.</em></td><td align="center"><a href="https://lectern.browsit.org/resources/resource/35-screaming-bedwars-quests-module/">Lectern</a> | <a href="https://www.spigotmc.org/resources/screaming-bedwars-module.98380/">SpigotMC</a></td><td><a href="../.gitbook/assets/icon_screaming_bedwars.png">icon_screaming_bedwars.png</a></td></tr></tbody></table>

### BedWars1058 💲 <a href="#bedwars1058-open-source" id="bedwars1058-open-source"></a>

![Ajoute les objectifs suivants:  "Démarrer l'arène", "Ouvrir la boutique", "Acheter un article", "Acheter une amélioration", "Détruire le lit", "Tuer le joueur" et "Fin de l'arène".](../.gitbook/assets/bedwars1058.jpg)

↳ [Téléchargement](https://www.spigotmc.org/resources/bedwars1058-quests-module.100722/)

***

### Boss 💲

![Ajoute un objectif "Kill Boss".](../.gitbook/assets/boss.png)

↳ [Téléchargement](https://www.spigotmc.org/resources/boss-quests-module.66973/) (nécessite Quests 3.6.0 ou plus récent)

***

### CustomMobs

![Ajoute un objectif "Kill CustomMobs".](../.gitbook/assets/custommobs.png)

{% tabs %}
{% tab title="Quests 5.0.0+" %}
[Téléchargement](https://www.spigotmc.org/resources/custommobs-quests-module.56686/)
{% endtab %}

{% tab title="4.0.7 - 4.8.3" %}
[Téléchargement](https://www.spigotmc.org/resources/custommobs-quests-module.56686/download?version=450058)
{% endtab %}

{% tab title="3.6.0 - 4.0.6" %}
[Téléchargement](https://www.spigotmc.org/resources/custommobs-quests-module.56686/)
{% endtab %}

{% tab title="3.2.7 - 3.5.9" %}
[Téléchargement](https://www.spigotmc.org/resources/custommobs-quests-module.56686/download?version=232903)
{% endtab %}

{% tab title="2.0.0  - 3.2.6" %}
[Téléchargement](https://www.spigotmc.org/resources/custommobs-quests.25679/)
{% endtab %}
{% endtabs %}

***

### DungeonsXL

![Ajoute les objectifs "Terminer le donjon", "Obtenir un objet de récompense", "Obtenir le niveau de récompense", "Obtenir de l'argent de récompense" et "Tuer la foule du donjon".](../.gitbook/assets/dungeonsxl.png)

↳ [Téléchargement](https://www.spigotmc.org/resources/dungeonsxl-quests-module.66703/) (nécessite Quests 3.6.0 ou plus récent)

***

### Interactions 💲

![Ajoute les objectifs "Démarrer la conversation" et "Terminer la conversation".](../.gitbook/assets/interactions.png)

↳ [Téléchargement](https://www.spigotmc.org/resources/interactions-quests-module.92421/)

***

### Magic

![Lien avec divers sorts et tâches magiques.](../.gitbook/assets/magic.png)

{% tabs %}
{% tab title="Quests 3.6.0 - 4.0.6" %}
[Téléchargement](http://jenkins.elmakers.com/job/MagicQuests/)
{% endtab %}

{% tab title="3.2.7 - 3.5.9" %}
[Téléchargement](https://jenkins.elmakers.com/job/MagicQuests/90/)
{% endtab %}

{% tab title="2.0.0  - 3.2.6" %}
[Téléchargement](https://jenkins.elmakers.com/job/MagicQuests/88/)
{% endtab %}
{% endtabs %}

***

### Marcely's Bedwars 💲

<figure><img src="https://public.marcely.de/data/img/products/mbedwars/v5/logo2.gif" alt="" width="375"><figcaption><p>Ajoute les objectifs suivants: "Démarrer l'arène", "Ouvrir la boutique", "Acheter un article", "Acheter une amélioration", "Détruire le lit", "Tuer le joueur" et "Fin de l'arène".</p></figcaption></figure>

↳ [Téléchargement](https://www.spigotmc.org/resources/marcelys-bedwars-quests-module.107857/)

***

### mcMMO Overhaul 💲

![Ajoute la récompense et l'exigence "Compétence".](../.gitbook/assets/mcmmo\_overhaul.png)

↳ [Téléchargement](https://www.spigotmc.org/resources/92962/) (nécessite Quests 4.0.0 ou plus récent)

{% hint style="info" %}
**Remarque:** Pour l'ancien mcMMO Classic, utilisez plutôt [cette dépendance](https://pikamug.gitbook.io/quests/v/french-francais/debutant/dependencies#mcmmo-classic)
{% endhint %}

***

### MobArena

![Ajoute les objectifs "Tuer les mobs", "Terminer la vague" et "Terminer l'arène".](../.gitbook/assets/mobarena.png)

↳ [Téléchargement](https://www.spigotmc.org/resources/mobarena-quests-module.72355/) (nécessite Quests 3.6.0 ou plus récent)

***

### MythicMobs 🌟💲

![Ajoute l'objectif "Kill MythicMobs" (tuer des monstres MythicMobs), ainsi que d'autres fonctionnalités selon la version.](../.gitbook/assets/mythicmobs.jpg)

{% tabs %}
{% tab title="Quests 5.0.0+" %}
[Téléchargement](https://lectern.browsit.org/resources/resource/48-mythicmobs-quests-module/)
{% endtab %}

{% tab title="4.0.7 - 4.8.3" %}
[Téléchargement](https://lectern.browsit.org/resources/resource/32-kill-mythic-mobs-multiplayer-improvement/)
{% endtab %}

{% tab title="3.6.0 - 4.0.6" %}
[Téléchargement](https://mc.hackerzlair.org/jenkins/job/MythicMobsQuests/)
{% endtab %}

{% tab title="3.2.7 - 3.5.9" %}
[Téléchargement](https://github.com/BerndiVader/MythicMobsQuestsModule/blob/a346d24545e874587c0895b30b369492978f6f81/MythicMobsQuests.jar)
{% endtab %}

{% tab title="2.0.0  - 3.2.6" %}
[Téléchargement](https://github.com/BerndiVader/MythicMobsQuestsModule/blob/edd5df5968628c06e5670c0e2a1c19ca41a86467/MythicMobsQuests285.jar)
{% endtab %}
{% endtabs %}

***

### NPCDestinations

![Ajoute les exigences de localisation et les récompenses des PNJ.](../.gitbook/assets/npcdestinations.png)

{% tabs %}
{% tab title="Quests 5.0.0+" %}
[Téléchargement](https://www.spigotmc.org/resources/101588/)
{% endtab %}

{% tab title="4.0.7 - 4.8.3" %}
[Téléchargement](https://www.spigotmc.org/resources/npcdestinations-quests-module.101588/download?version=449913)
{% endtab %}

{% tab title="3.6.0 - 4.0.6" %}
Le module est installé automatiquement avec NPCDestinations.
{% endtab %}
{% endtabs %}

***

### PhatLoots

![Ajoute des récompenses de butin et des objectif.](https://i.imgur.com/yHiPJFh.png)

↳ [Téléchargement](https://www.spigotmc.org/resources/phatloots-quests-module.102525/)

***

### Proskillapi

<figure><img src="https://www.spigotmc.org/data/resource_icons/91/91913.jpg" alt=""><figcaption><p>Ajoute des exigences de classe et des récompenses.</p></figcaption></figure>

↳ [Téléchargement](https://www.spigotmc.org/resources/91913/) (le module est installé automatiquement par Proskillapi)

***

### Screaming BedWars 💲

![Ajoute les objectifs suivants: "Démarrer l'arène", "Ouvrir la boutique", "Acheter un article", "Acheter une amélioration", "Détruire le lit", "Tuer le joueur" et "Fin de l'arène".](https://www.spigotmc.org/data/resource\_icons/63/63714.jpg)

↳ [Téléchargement](https://www.spigotmc.org/resources/screaming-bedwars-module.98380/)

***

### Vous souhaitez une assistance pour d'autres plugins ou fonctionnalités ?

Si vous ne trouvez pas de module pour un usage particulier ici ou via une recherche sur Internet, envisagez d'embaucher un développeur sur l'un de ces sites :

* [Quests Community](https://discordapp.com/invite/QdJAv2G7qg)
* [SpigotMC](https://www.spigotmc.org/forums/hiring-developers.55/)
* [Lectern](https://lectern.browsit.org/forum/view/6-services/)

Ni Quests ni ses contributeurs ne sont responsables de la qualité et/ou de la fonctionnalité des modules tiers, implicites ou non, quelle que soit leur origine.
