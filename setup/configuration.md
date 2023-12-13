# Configuration

When Quests is first run, configuration files will be created in the /plugins/Quests directory. If this is your first time using Quests, just make sure the settings in **config.yml** are to your liking. Don't worry about any of the other files or folders for the time being.

{% hint style="info" %}
**Pro-tip:** Opening a .yml file that contains non-English characters on an English computer may not display those characters correctly. In the case of Windows, this is because Windows in English uses the ANSI character set, while the preferred format is UTF-8. Unfortunately, Windows makes this difficult to change, so we recommend an editing program that supports UTF-8. [Notepad++](https://notepad-plus-plus.org/) is a free and popular choice.
{% endhint %}

### config.yml

This file contains all settings relating to how Quests should perform once loaded. As such, changes made to this file must be configured and saved _before_ the server is started.

> [Click here to view the default config.yml file.](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/config.yml)

| Key                                           | Data Type  | Description                                                                                                                                                    |
| --------------------------------------------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| accept-timeout                                | number     | How long (in seconds) a player should be able to accept/deny a quest before the prompt cancels automatically.                                                  |
| allow-command-questing                        | true/false | Whether players are allowed to accept and manage quests via command (e.g. /quests take SomeQuest).                                                             |
| allow-command-quests-with-npcs                | true/false | Whether players can accept/manage NPC quests via command (e.g. /quests take SomeQuest).                                                                        |
| allow-pranks                                  | true/false | Whether to permit clicking Portals with the Quests Journal.                                                                                                    |
| clickable-prompts                             | true/false | Click most prompt selections in chat.                                                                                                                          |
| condition-interval                            | number     | How long (in seconds) between condition notifications (min. 3, max. 180).                                                                                      |
| confirm-accept                                | true/false | Whether players must confirm taking of a quest.                                                                                                                |
| confirm-abandon                               | true/false | Whether players must confirm quitting of a quest.                                                                                                              |
| console-logging                               | number     | 0 = disabled, 1 = track editing, 2 = and start/quit quests, 3 = and rewards, 4 = and debug information.                                                        |
| disable-command-feedback                      | true/false | Whether to disable Minecraft's sendCommandFeedback gamerule at startup.                                                                                        |
| generate-files-on-join                        | true/false | Either generate a player data file when that player first joins the server or only when they first use Quests.                                                 |
| give-journal-item                             | true/false | Quest Journal exists as item in player inventory.                                                                                                              |
| ignore-locked-quests                          | true/false | Ignore locked quests when checking if a player has all necessary Requirements.                                                                                 |
| kill-delay                                    | number     | How long (in seconds) a player should have to wait after they kill a player for a quest before they can kill that player again.                                |
| language                                      | string     | Which file from the /lang/ folder will be used for administrative text. For example, a value of "FR-fr" will result in "/lang/FR-fr/strings.yml" being loaded. |
| language-override-client                      | true/false | Whether `language` setting should override client language when sending text.                                                                                  |
| max-quests                                    | number     | Maximum number of quests a given player can have at any time.                                                                                                  |
| npc-effects.enabled                           | true/false | Whether to enable particle effects. Note that the client must have particles enabled.                                                                          |
| npc-effects.new-quest                         | string     | The particle effect to be played for a new quest (ex. note, enchant, crit, spell, portal).                                                                     |
| npc-effects.redo-quest                        | string     | The particle effect to be played for a repeatable quest (ex. note, enchant, crit, spell, portal).                                                              |
| show-requirements                             | true/false | Allow players to see requirements in /quest \[quest]                                                                                                           |
| show-titles                                   | true/false | Display titles to players when accepting/completing quests.                                                                                                    |
| strict-player-movement                        | number     | Seconds between advanced player movement tracking.                                                                                                             |
| storage-data.address                          | string     | The IP address for optional storage.                                                                                                                           |
| storage-data.database                         | string     | The table name for optional storage.                                                                                                                           |
| storage-data.username                         | string     | The login username for optional storage.                                                                                                                       |
| storage-data.password                         | string     | The login password for optional storage.                                                                                                                       |
| storage-data.pool-settings.max-pool-size      | number     | Advanced HikariCP setting.                                                                                                                                     |
| storage-data.pool-settings.min-idle           | number     | Advanced HikariCP setting.                                                                                                                                     |
| storage-data.pool-settings.max-lifetime       | number     | Advanced HikariCP setting.                                                                                                                                     |
| storage-data.pool-settings.connection-timeout | number     | Advanced HikariCP setting.                                                                                                                                     |
| storage-method.player-data                    | string     | yaml = file storage, mysql = remote storage, custom = developer storage                                                                                        |
| top-limit                                     | number     | Maximum number of quests that can be displayed by /quests top \[number]                                                                                        |
| translate-names                               | true/false | Translate item/mob name to client's game language.                                                                                                             |
| translate-subcommands                         | true/false | Translate subcommands to server's plugin language.                                                                                                             |
| trial-save                                    | true/false | Allow saving while in Trial Mode.                                                                                                                              |
| update-check                                  | true/false | Whether to permit checking for plugin updates.                                                                                                                 |

### actions.yml

{% hint style="info" %}
Manually editing this file is not advised. No support will be given to those whom choose not to use the in-game editor.
{% endhint %}

This file holds actions which execute certain tasks and effects. Except for the included examples, actions are created prior to use in a Quest. This is best accomplished with the _/quests actions_ command.

> [Click here to view the default actions.yml file.](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/actions.yml)

### conditions.yml

{% hint style="info" %}
Manually editing this file is not advised. No support will be given to those whom choose not to use the in-game editor.
{% endhint %}

This file holds conditions which are checked during gameplay. Except for the included examples, conditions are created prior to use in a Quest. This is best accomplished with the _/quests conditions_ command.

> [Click here to view the default conditions.yml file.](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/conditions.yml)

### quests.yml

{% hint style="info" %}
Manually editing this file is not advised. No support will be given to those whom choose not to use the in-game editor.
{% endhint %}

This file contains all saved quests. A few example quests are included which you may delete at any time. This is best accomplished with the _/quests editor_ command.

> [Click here to view the default quests.yml file.](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/quests.yml)
