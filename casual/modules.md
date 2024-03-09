# Modules

{% hint style="info" %}
**Notice:** This information is intended for intermediate users. Read carefully!
{% endhint %}

Plugins which integrate with Quests to provide Custom Objectives, Rewards and Requirements, use what are known as _modules_. A module is a jar file created by developers using the [Quests API](https://github.com/PikaMug/Quests/wiki/Master-%E2%80%90-Custom-Quest-API), which acts as a middleman between Quests and the integrating plugin. This is in contrast to a [dependency](https://github.com/PikaMug/Quests/wiki/Beginner-%E2%80%90-Dependencies), which you typically do not need a module for.

Module jars must be placed in the _Quests/modules_ folder, while the target plugin goes in the _/plugins_ folder as usual. Note that all modules are entirely optional and you may add or remove them as seen fit. Below is an incomplete list of popular plugins for which a module is known to exist, along with a description of how it links.

| Labels:                                      |                                               |
| -------------------------------------------- | --------------------------------------------- |
| 🌟 = Recommended for optimal user experience | 💲 = May require purchase of premium resource |

### BedWars1058 💲

![Adds "Start arena", "Open shop", "Buy item", "Buy upgrade", "Destroy bed", "Kill player", and "End arena" objectives.](../.gitbook/assets/bedwars1058.jpg)

↳ [Download](https://www.spigotmc.org/resources/bedwars1058-quests-module.100722/)

***

### Boss 💲

![Adds a "Kill Boss" objective.](../.gitbook/assets/boss.png)

↳ [Download](https://www.spigotmc.org/resources/boss-quests-module.66973/) (requires Quests 3.6.0 or newer)

***

### CustomMobs

![Adds a "Kill CustomMobs" objective.](../.gitbook/assets/custommobs.png)

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

***

### DungeonsXL

![Adds "Finish dungeon", "Get reward item", "Get reward level", "Get reward money", and "Kill dungeon mob" objectives.](../.gitbook/assets/dungeonsxl.png)

↳ [Download](https://www.spigotmc.org/resources/dungeonsxl-quests-module.66703/) (requires Quests 3.6.0 or newer)

***

### Interactions 💲

![Adds "Start conversation" and "End conversation" objectives.](../.gitbook/assets/interactions.png)

↳ [Download](https://www.spigotmc.org/resources/interactions-quests-module.92421/)

***

### Magic

![Link with various Magic spells and tasks.](../.gitbook/assets/magic.png)

{% tabs %}
{% tab title="Quests 3.6.0 - 4.0.6" %}
[Download](http://jenkins.elmakers.com/job/MagicQuests/)
{% endtab %}

{% tab title="3.2.7 - 3.5.9" %}
[Download](https://jenkins.elmakers.com/job/MagicQuests/90/)
{% endtab %}

{% tab title="2.0.0  - 3.2.6" %}
[Download](https://jenkins.elmakers.com/job/MagicQuests/88/)
{% endtab %}
{% endtabs %}

***

### Marcely's Bedwars 💲

<figure><img src="https://public.marcely.de/data/img/products/mbedwars/v5/logo2.gif" alt="" width="375"><figcaption><p>Adds "Start arena", "Open shop", "Buy item", "Buy upgrade", "Destroy bed", "Kill player", and "End arena" objectives.</p></figcaption></figure>

↳ [Download](https://www.spigotmc.org/resources/marcelys-bedwars-quests-module.107857/)

***

### mcMMO Overhaul 💲

![Adds "Skill" reward and requirement.](../.gitbook/assets/mcmmo\_overhaul.png)

↳ [Download](https://www.spigotmc.org/resources/92962/) (requires Quests 4.0.0 or newer)

{% hint style="info" %}
**Note:** For the older mcMMO Classic, use [this dependency](https://pikamug.gitbook.io/quests/v/spanish-espanol/beginner/dependencies#mcmmo-classic) instead.
{% endhint %}

***

### MobArena

![Adds "Kill mobs", "Finish wave", and "Complete arena" objectives.](../.gitbook/assets/mobarena.png)

↳ [Download](https://www.spigotmc.org/resources/mobarena-quests-module.72355/) (requires Quests 3.6.0 or newer)

***

### MythicMobs 🌟💲

![Adds "Kill MythicMobs" objective, plus other features depending on version.](../.gitbook/assets/mythicmobs.jpg)

{% tabs %}
{% tab title="Quests 5.0.0+" %}
[Download](https://lectern.browsit.org/resources/resource/48-mythicmobs-quests-module/)
{% endtab %}

{% tab title="4.8.3 - 4.0.7" %}
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

***

### NPCDestinations

![Adds NPC location requirements and reward.](../.gitbook/assets/npcdestinations.png)

{% tabs %}
{% tab title="Quests 5.0.0+" %}
[Download](https://www.spigotmc.org/resources/101588/)
{% endtab %}

{% tab title="4.8.3 - 4.0.7" %}
[Download](https://www.spigotmc.org/resources/npcdestinations-quests-module.101588/download?version=449913)
{% endtab %}

{% tab title="3.6.0 - 4.0.6" %}
Module is auto-installed by NPCDestinations.
{% endtab %}
{% endtabs %}

***

### PhatLoots

![Adds loot reward and objective.](https://i.imgur.com/yHiPJFh.png)

↳ [Download](https://www.spigotmc.org/resources/phatloots-quests-module.102525/)

***

### Proskillapi

<figure><img src="https://www.spigotmc.org/data/resource_icons/91/91913.jpg" alt=""><figcaption><p>Adds class requirements and rewards.</p></figcaption></figure>

↳ [Download](https://www.spigotmc.org/resources/91913/) (el módulo es instalado automáticamente por Proskillapi)

***

### Screaming BedWars 💲

![Adds "Start arena", "Open shop", "Buy item", "Buy upgrade", "Destroy bed", "Kill player", and "End arena" objectives.](https://www.spigotmc.org/data/resource\_icons/63/63714.jpg)

↳ [Download](https://www.spigotmc.org/resources/screaming-bedwars-module.98380/)

***

### Want support for other plugins or features?

If you can't find a module for a particular purpose here or via Internet search, consider hiring a developer at one of these sites:

* [Quests Community](https://discordapp.com/invite/QdJAv2G7qg)
* [SpigotMC](https://www.spigotmc.org/forums/hiring-developers.55/)
* [Lectern](https://lectern.browsit.org/forum/view/6-services/)

Quests is not sponsored by any of the sites above. Neither Quests nor its contributors hold any responsibility for the quality and/or functionality of third-party modules, implied or otherwise, regardless of origin.
