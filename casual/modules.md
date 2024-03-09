# Модули

{% hint style="info" %}
**Забележка:** Тази информация е предназначена за средно напреднали потребители. Прочети внимателно!
{% endhint %}

Плъгините, които се интегрират с Quests, за да предоставят персонализирани цели, награди и изисквания, използват това, което е известно като _модули_. Модулут е jar файл, създаден от разработчици, използващи [Quests API](../master/custom-quest-api.md), който действа като посредник между Quests и интегриращия плъгин. Това е в контраст с [зависимости](../beginner/dependencies.md), за което обикновено не се нуждаете от модул.

Модул файловете трябва да бъдат поставени в папка _Quests/modules_ докато целевият плъгин отива в папката _/plugins_ както обикновено. Имайте предвид, че всички модули са изцяло незадължителни и можете да ги добавяте или премахване, както сметнете за добре. По-долу е даден непълен списък с популярни плъгини, за които е известно, че съществува модул, заедно с описание на това как се свързва.

| Етикети:                                               |                                                   |
| ------------------------------------------------------ | ------------------------------------------------- |
| 🌟 = Препоръчва се за оптимално потребилско изживяване | 💲 = Може да изисква закупуване на премиум ресурс |

### BedWars1058 💲

![Добавя "Start arena", "Open shop", "Buy item", "Buy upgrade", "Destroy bed", "Kill player" и "End arena" цели.](../.gitbook/assets/bedwars1058.jpg)

↳ [Изтегляне](https://www.spigotmc.org/resources/bedwars1058-quests-module.100722/)

### Boss 💲

![Добавя цел "Kill Boss".](../.gitbook/assets/boss.png)

↳ [Изтегляне](https://www.spigotmc.org/resources/boss-quests-module.66973/) (Изисква Quests 3.6.0 или по нов)

### CustomMobs

![Добавя цел "Kill CustomMobs".](../.gitbook/assets/custommobs.png)

{% tabs %}
{% tab title="Quests 3.6.0+" %}
[Изтегляне](https://www.spigotmc.org/resources/custommobs-quests-module.56686/)
{% endtab %}

{% tab title="3.2.7 - 3.5.9" %}
[Изтегляне](https://www.spigotmc.org/resources/custommobs-quests-module.56686/download?version=232903)
{% endtab %}

{% tab title="2.0.0  - 3.2.6" %}
[Изтегляне](https://www.spigotmc.org/resources/custommobs-quests.25679/)
{% endtab %}
{% endtabs %}

### DungeonsXL

![Добавя цели "Finish dungeon", "Get reward item", "Get reward level", "Get reward money" и "Kill dungeon mob".](../.gitbook/assets/dungeonsxl.png)

↳ [Изтегляне](https://www.spigotmc.org/resources/dungeonsxl-quests-module.66703/) (изисква Quests 3.6.0 или по нов)

### Interactions 💲

![Добавя цели "Start conversation" и "End conversation".](../.gitbook/assets/interactions.png)

↳ [Изтегляне](https://www.spigotmc.org/resources/interactions-quests-module.92421/)

### Magic

![Връзка с различни магически заклинания и задачи.](../.gitbook/assets/magic.png)

{% tabs %}
{% tab title="Quests 3.6.0 - 4.0.6" %}
[Изтегляне](http://jenkins.elmakers.com/job/MagicQuests/)
{% endtab %}

{% tab title="3.2.7 - 3.5.9" %}
[Изтегляне](https://jenkins.elmakers.com/job/MagicQuests/90/)
{% endtab %}

{% tab title="2.0.0  - 3.2.6" %}
[Изтегляне](https://jenkins.elmakers.com/job/MagicQuests/88/)
{% endtab %}
{% endtabs %}

### Marcely's Bedwars 💲

<figure><img src="https://public.marcely.de/data/img/products/mbedwars/v5/logo2.gif" alt="" width="375"><figcaption><p>Добавя "Start arena", "Open shop", "Buy item", "Buy upgrade", "Destroy bed", "Kill player", и "End arena" цели.</p></figcaption></figure>

↳ [Изтегляне](https://www.spigotmc.org/resources/marcelys-bedwars-quests-module.107857/)

### mcMMO Overhaul 💲

![Добавя "Skill" награда и изискване.](../.gitbook/assets/mcmmo\_overhaul.png)

↳ [Изтегляне](https://www.spigotmc.org/resources/92962/) (изисква Quests 4.0.0 или по нов)

{% hint style="info" %}
**Забележка:** за по стари версии на mcMMO Classic, използвайте вместо това [тази зависимост](https://pikamug.gitbook.io/quests/beginner/dependencies#mcmmo-classic).
{% endhint %}

### MobArena

![Добавя цели "Kill mobs", "Finish wave", и "Complete arena".](../.gitbook/assets/mobarena.png)

↳ [Изтегляне](https://www.spigotmc.org/resources/mobarena-quests-module.72355/) (изисква Quests 3.6.0 или по нов)

### MythicMobs 🌟💲

![Добавя цел "Kill MythicMobs", плюс други функции в зависимост от версията.](../.gitbook/assets/mythicmobs.jpg)

{% tabs %}
{% tab title="Quests 5.0.0+" %}
[Изтегляне](https://lectern.browsit.org/resources/resource/48-mythicmobs-quests-module/)
{% endtab %}

{% tab title="4.8.3 - 4.0.7" %}
[Изтегляне](https://lectern.browsit.org/resources/resource/32-kill-mythic-mobs-multiplayer-improvement/)
{% endtab %}

{% tab title="3.6.0 - 4.0.6" %}
[Изтегляне](https://mc.hackerzlair.org/jenkins/job/MythicMobsQuests/)
{% endtab %}

{% tab title="3.2.7 - 3.5.9" %}
[Изтегляне](https://github.com/BerndiVader/MythicMobsQuestsModule/blob/a346d24545e874587c0895b30b369492978f6f81/MythicMobsQuests.jar)
{% endtab %}

{% tab title="2.0.0  - 3.2.6" %}
[Изтегляне](https://github.com/BerndiVader/MythicMobsQuestsModule/blob/edd5df5968628c06e5670c0e2a1c19ca41a86467/MythicMobsQuests285.jar)
{% endtab %}
{% endtabs %}

### NPCDestinations

![Добавя изисквания за местоположение на NPC и награда.](../.gitbook/assets/npcdestinations.png)

{% tabs %}
{% tab title="Quests 4.0.6+" %}
[Изтегляне](https://www.spigotmc.org/resources/101588/)
{% endtab %}

{% tab title="3.6.0 - 4.0.6" %}
Модула се инсталира автоматично от NPCDestinations.
{% endtab %}
{% endtabs %}

### PhatLoots

![Добавя плячка, награда и цел.](https://i.imgur.com/yHiPJFh.png)

↳ [Изтегляне](https://www.spigotmc.org/resources/phatloots-quests-module.102525/)

### Proskillapi

<figure><img src="https://www.spigotmc.org/data/resource_icons/91/91913.jpg" alt=""><figcaption><p>Добавя изисквания за клас и награди.</p></figcaption></figure>

↳ [Изтегляне](https://www.spigotmc.org/resources/91913/) (модулът се инсталира автоматично от Proskillapi)

### Screaming BedWars 💲

![Добавя "Start arena", "Open shop", "Buy item", "Buy upgrade", "Destroy bed", "Kill player" и "End arena" цели.](https://www.spigotmc.org/data/resource\_icons/63/63714.jpg)

↳ [Изтегляне](https://www.spigotmc.org/resources/screaming-bedwars-module.98380/)

### Искате поддръжка за други добавки или функции?

Ако не можете да намерите модул за определена цел тук или чрез търсене в Интернет, помислете за наемане на програмист в един от тези сайтове:

* [Quests Community](https://discordapp.com/invite/QdJAv2G7qg)
* [SpigotMC](https://www.spigotmc.org/forums/hiring-developers.55/)
* [Lectern](https://lectern.browsit.org/forum/view/6-services/)

Нито Quests, нито неговите сътрудници носят никаква отговорност за качеството и/или фукционалността на модуле на трети страни, подразбиращи се или по друг начин, независимо от произхода.
