# Команди и разрешения

Трите основни команди за Quests са **/quests**, **/quest** и **/questadmin**. Първите две са активирани за всички потребители по подразбиране, докато последната е запазена за сървърни оператори. За да промените това поведение, като например да дадете **\questadmin** на не OP Администратори, трябва да настроите [разрешения](https://bukkit.gamepedia.com/Understanding\_Permissions).

### Команди на играча

По-долу има диаграма, която описва всяка команда и свързаното с нея разрешение. Обърнете внимание, че подкомандите (list, take, quit и др.) могат да се променят, ако вие [изберете друг език за плъгина](https://github.com/PikaMug/Quests/wiki/Translations), но разрешенията ще останат същите.

| Команда               | Разрешение       | Описание                                   |
| --------------------- | ---------------- | ------------------------------------------ |
| /quests               | quests.quests    | Показва помощ за плъгина                   |
| /quests list \[page]  | quests.list      | Списък със всички налични задачи           |
| /quests take \[quest] | quests.take      | Приеми задача чрез команда                 |
| /quests quit \[quest] | quests.quit      | Напусни сегашната си задача                |
| /quests stats         | quests.stats     | Вижте вашата статистика за задачи          |
| /quests top \[number] | quests.top       | Вижте класациите на плъгина                |
| /quests info          | quests.info      | Вижте информация за плъгина                |
| /quests journal       | quests.journal   | Превключете вашия дневник за задачи        |
| N/A                   | quests.compass   | Проследявайте задачи с помощта на компас   |
| N/A                   | quests.choice    | Използвайте текст с възможност за кликване |
|                       |                  |                                            |
| /quest                | quests.quest     | Вижте текущите цели на задачата            |
| /quest \[quest]       | quests.questinfo | Вижте информация за задачата               |

{% hint style="info" %}
**Професионален съвет:** По подразбиране можете също да използвате **/qs** и **/q** вместо **/quests** и **/quest**!
{% endhint %}

### Администраторски команди

Командите на администратора, които трябва да се предоставят само на онези, на които имате доверие, за да не ги злоупотребяват, са описани по-долу.

| Команда                                          | Разрешение               | Описани                                                    |
| ------------------------------------------------ | ------------------------ | ---------------------------------------------------------- |
| /questadmin                                      | quests.admin             | Показва помощ за администратори                            |
| /questadmin stats \[player]                      | quests.admin.stats       | Прегледайте статистиката на играч                          |
| /questadmin give \[player] \[quest]              | quests.admin.give        | Принудете играч да приеме задача                           |
| /questadmin quit \[player] \[quest]              | quests.admin.quit        | Принудете играч да напусне задача                          |
| /questadmin points \[player] \[amount]           | quests.admin.points      | Задайте Точки на играча                                    |
| /questadmin takepoints \[player] \[amount]       | quests.admin.takepoints  | Вземете Точки на играча                                    |
| /questadmin givepoints \[player] \[amount]       | quests.admin.givepoints  | Добавете Точки на играча                                   |
| /questadmin finish \[player] \[quest]            | quests.admin.finish      | Принудете играч да завърши задачата                        |
| /questadmin nextstage \[player] \[quest]         | quests.admin.nextstage   | Принудете играч да завърши сегашния си етап                |
| /questadmin setstage \[player] \[quest] \[stage] | quests.admin.setstage    | Задайте сегашен етап за играч                              |
| /questadmin reset \[player]                      | quests.admin.reset       | Изчистете всичките информация за играч                     |
| /questadmin remove \[player] \[quest]            | quests.admin.remove      | Премахнете завършена задача от играч                       |
| /questadmin reload                               | quests.admin.reload      | Презаредете плъгина                                        |
| N/A                                              | quests.admin.drop        | Позволете на играч да хвърля дневника за задачите          |
| N/A                                              | quests.admin.update      | Вижте известия за актиализации на плъгина                  |
| N/A                                              | quests.mode.trial        | Ограничен достъп за редактори, деактивиран по подразбиране |
| /quests editor                                   | quests.editor.editor     | Възможност да отваряте редактора на задачи                 |
| N/A                                              | quests.editor.create     | Възможност за създаване на нови задачи                     |
| N/A                                              | quests.editor.edit       | Възможност за редактиране на съществуващи задачи           |
| N/A                                              | quests.editor.delete     | Възможност за изтриване на съществуващи задача             |
| /quests actions                                  | quests.actions.editor    | Възможност за отваряне на редактора на действия            |
| N/A                                              | quests.actions.create    | Възможност за създаване на нови действия                   |
| N/A                                              | quests.actions.edit      | Възможност за редактиране на съществуващи действия         |
| N/A                                              | quests.actions.delete    | Възможност за изтриване на съществуващи действия           |
| /quests conditions                               | quests.conditions.editor | Възможност за отваряне на редактора на условия             |
| N/A                                              | quests.conditions.create | Възможност за създаване на условия                         |
| N/A                                              | quests.conditions.edit   | Възможност за редактиране на съществуващи условия          |
| N/A                                              | quests.conditions.delete | Възможност за изтриване на съществуващи условия            |

{% hint style="info" %}
**Професионален съвет:** Използвайте _quests.admin.\*_, _quests.editor.\*_, _quests.actions.\*_ and _quests.conditions.\*_ за да обхванете съответно всички администраторски и редакторски разрешения! по подразбиране можете също да използвате **/qa** вместо **/questadmin**!
{% endhint %}
