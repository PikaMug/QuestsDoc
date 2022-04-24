# Modules

{% hint style="info" %}
**Notice:** This information is intended for intermediate users. Read carefully!
{% endhint %}

Plugins which integrate with Quests to provide Custom Objectives, Rewards and Requirements, use what are known as _modules_. A module is a jar file created by developers using the [Quests API](https://github.com/PikaMug/Quests/wiki/Master-%E2%80%90-Custom-Quest-API), which acts as a middleman between Quests and the integrating plugin. This is in contrast to a [dependency](https://github.com/PikaMug/Quests/wiki/Beginner-%E2%80%90-Dependencies), which you typically do not need a module for.

Module jars must be placed in the _Quests/modules_ folder, while the target plugin goes in the _/plugins_ folder as usual. Note that all modules are entirely optional and you may add or remove them as seen fit. Below is an incomplete list of popular plugins for which a module is known to exist, along with a description of how it links.

| Labels:                                      |                                               |
| -------------------------------------------- | --------------------------------------------- |
| 🌟 = Recommended for optimal user experience | 💲 = May require purchase of premium resource |

### BedWars1058 - Open Source 💲

![Adds "Start arena", "Open shop", "Buy item", "Buy upgrade", "Destroy bed", "Kill player", and "End arena" objectives.](../.gitbook/assets/bedwars1058.jpg)

↳ [Download](https://www.spigotmc.org/resources/bedwars1058-quests-module.100722/)

### Boss 💲

![](https://camo.githubusercontent.com/53192d923a6add754608ffd62dae992b9963ebbc72635ac313027ea8dd0632e9/68747470733a2f2f692e696d6775722e636f6d2f68793653754b392e706e67)

↳ [Download](https://www.spigotmc.org/resources/boss-quests-module.66973/) (requires Quests 3.6.0 or newer)

### CustomMobs

![Adds a "Kill CustomMobs" objective.](https://camo.githubusercontent.com/6029eb00543fc07c423a8818389bb53d679c4be330064631bc7d8aa2d0d1a86a/68747470733a2f2f692e696d6775722e636f6d2f79446e32704c632e706e67)

{% tabs %}
{% tab title="Quests 3.6.0+" %}
[Download](https://www.spigotmc.org/resources/custommobs-quests-module.56686/)
{% endtab %}

{% tab title="3.2.7 - 3.5.9" %}
[Download](https://www.spigotmc.org/resources/custommobs-quests-module.56686/download?version=232903)
{% endtab %}

{% tab title="2.0.0  - 3.2.6" %}
[Download](https://www.spigotmc.org/resources/custommobs-quests.25679/)
{% endtab %}
{% endtabs %}

### DungeonsXL

![Adds "Finish dungeon", "Get reward item", "Get reward level", "Get reward money", and "Kill dungeon mob" objectives.](https://camo.githubusercontent.com/70fecf6dfd0399b3a64f8a16d94dd3d7cf928178d92c9f180a7f3345117fdc78/687474703a2f2f65726574686f6e2e64652f7265736f75726365732f6c6f676f732f44756e67656f6e73584c2e706e67)

↳ [Download](https://www.spigotmc.org/resources/dungeonsxl-quests-module.66703/) (requires Quests 3.6.0 or newer)

### Interactions 💲

![Adds "Start conversation" and "End conversation" objectives.](../.gitbook/assets/976a91ee01f5c7d5c20de730115b3e93bf604244.png)

↳ [Download](https://www.spigotmc.org/resources/interactions-quests-module.92421/)

### Magic

![Link with various Magic spells and tasks.](https://camo.githubusercontent.com/d9ef4d8eb088489debd7f72e65cbf67f6a682f9c3d36e41a4b3a3747b635ab92/68747470733a2f2f692e696d6775722e636f6d2f453155344361522e706e67)

{% tabs %}
{% tab title="Quests 3.6.0+" %}
[Download](http://jenkins.elmakers.com/job/MagicQuests/)
{% endtab %}

{% tab title="3.2.7 - 3.5.9" %}
[Download](https://jenkins.elmakers.com/job/MagicQuests/90/)
{% endtab %}

{% tab title="2.0.0  - 3.2.6" %}
[Download](https://jenkins.elmakers.com/job/MagicQuests/88/)
{% endtab %}
{% endtabs %}

### mcMMO Overhaul 💲

![Adds "Skill" reward and requirement.](https://camo.githubusercontent.com/8f19026fc09827670ad5f270b6865286c135f18de8400bd3de55402fd49a165f/68747470733a2f2f692e696d6775722e636f6d2f655575427247522e706e67)

↳ [Download](https://www.spigotmc.org/resources/92962/) (requires Quests 4.0.0 or newer)

{% hint style="info" %}
**Note:** For the older mcMMO Classic, use [this dependency](https://pikamug.gitbook.io/quests/v/spanish-espanol/beginner/dependencies#mcmmo-classic) instead.
{% endhint %}

### MobArena

![Adds "Kill mobs", "Finish wave", and "Complete arena" objectives.](https://camo.githubusercontent.com/c0d2e237c6293ada28cce473aa0578a0246f045ec75ed26a38054d8b6564f034/68747470733a2f2f692e696d6775722e636f6d2f733874715944702e706e67)

↳ [Download](https://www.spigotmc.org/resources/mobarena-quests-module.72355/) (requires Quests 3.6.0 or newer)

### MythicMobs 🌟💲

![Adds "Kill MythicMobs" objective, plus other features depending on version.](https://camo.githubusercontent.com/aebb3e692cec287e8baddc103a16e47bfb986dd861678a461e799e7cf240ebfc/68747470733a2f2f692e696d6775722e636f6d2f7a6c776f31304c2e706e67)

{% tabs %}
{% tab title="Quests 4.0.6+" %}
[Download](https://lectern.browsit.org/resources/resource/32-kill-mythic-mobs-multiplayer-improvement/)
{% endtab %}

{% tab title="3.6.0 - 4.0.6" %}
[Download](https://mc.hackerzlair.org/jenkins/job/MythicMobsQuests/)
{% endtab %}

{% tab title="3.2.7 - 3.5.9" %}
[Download](https://github.com/BerndiVader/MythicMobsQuestsModule/blob/a346d24545e874587c0895b30b369492978f6f81/MythicMobsQuests.jar)
{% endtab %}

{% tab title="2.0.0  - 3.2.6" %}
[Download](https://github.com/BerndiVader/MythicMobsQuestsModule/blob/edd5df5968628c06e5670c0e2a1c19ca41a86467/MythicMobsQuests285.jar)
{% endtab %}
{% endtabs %}

### NPCDestinations

![Adds NPC location requirements and reward.](https://camo.githubusercontent.com/5703b4f519542e8fe21a9296a5a0c291744b13b0be8547b450baa729c1f6669a/68747470733a2f2f692e696d6775722e636f6d2f59504942596b462e706e67)

{% tabs %}
{% tab title="Quests 4.0.6+" %}
[Download](https://www.spigotmc.org/resources/101588/)
{% endtab %}

{% tab title="3.6.0 - 4.0.6" %}
Module is auto-installed by NPCDestinations.
{% endtab %}
{% endtabs %}

### Screaming BedWars 💲

![Adds "Start arena", "Open shop", "Buy item", "Buy upgrade", "Destroy bed", "Kill player", and "End arena" objectives.](https://www.spigotmc.org/data/resource\_icons/63/63714.jpg)

↳ [Download](https://www.spigotmc.org/resources/screaming-bedwars-module.98380/)

### Want support for other plugins or features?

If you can't find a module for a particular purpose here or via Internet search, consider hiring a developer at one of these sites:

* [Quests Community](https://discordapp.com/invite/QdJAv2G7qg)
* [SpigotMC](https://www.spigotmc.org/forums/hiring-developers.55/)
* [Lectern](https://lectern.browsit.org/forum/view/6-services/)

Quests is not sponsored by any of the sites above. Neither Quests nor its contributors hold any responsibility for the quality and/or functionality of third-party modules, implied or otherwise, regardless of origin.
