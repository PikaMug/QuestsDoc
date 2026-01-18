# 配置

首次运行Quests时,配置文件将在 /plugins/Quests 目录中创建。如果您是第一次使用Quests,只需确保 **config.yml** 中的设置符合您的喜好即可。暂时不要担心其他文件或文件夹。

{% hint style="info" %}
**专业提示:** 在英文计算机上打开包含非英文字符的.yml文件可能无法正确显示这些字符。对于Windows系统,这是因为英文版Windows使用ANSI字符集,而首选格式是UTF-8。不幸的是,Windows使更改变得困难,因此我们推荐支持UTF-8的编辑程序。[Notepad++](https://notepad-plus-plus.org/) 是一个免费且受欢迎的选择。
{% endhint %}

### config.yml

此文件包含Quests加载后应如何执行的所有相关设置。因此,对此文件所做的更改必须在服务器启动_之前_配置并保存。

> [点击此处查看默认的config.yml文件。](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/config.yml)

| 键                                             | 数据类型   | 描述                                                                                                                                                          |
| --------------------------------------------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| accept-timeout                                | 数字       | 玩家在提示自动取消之前能够接受/拒绝任务的时间(秒)。                                                                                                                  |
| allow-command-questing                        | true/false | 是否允许玩家通过命令接受和管理任务(例如 /quests take SomeQuest)。                                                                                             |
| allow-command-quests-with-npcs                | true/false | 玩家是否可以通过命令接受/管理NPC任务(例如 /quests take SomeQuest)。                                                                                           |
| allow-pranks                                  | true/false | 是否允许使用任务日志点击传送门。                                                                                                                              |
| clickable-prompts                             | true/false | 在聊天中点击大多数提示选择。                                                                                                                                  |
| condition-interval                            | 数字       | 条件通知之间的时间(秒)(最小3,最大180)。                                                                                                                        |
| confirm-abandon                               | true/false | 玩家是否必须确认放弃任务。                                                                                                                                   |
| confirm-accept                                | true/false | 玩家是否必须确认接受任务。                                                                                                                                   |
| console-logging                               | 数字       | 0 = 禁用,1 = 跟踪编辑,2 = 和开始/放弃任务,3 = 和奖励,4 = 和调试信息。                                                                                           |
| disable-command-feedback                      | true/false | 是否在启动时禁用Minecraft的sendCommandFeedback游戏规则。                                                                                                        |
| generate-files-on-join                        | true/false | 在玩家首次加入服务器时生成玩家数据文件,还是仅在首次使用Quests时生成。                                                                                            |
| give-journal-item                             | true/false | 任务日志作为物品存在于玩家背包中。                                                                                                                            |
| ignore-locked-quests                          | true/false | 检查玩家是否具备所有必要要求时忽略已锁定的任务。                                                                                                               |
| kill-delay                                    | 数字       | 玩家为任务杀死玩家后,必须等待多长时间(秒)才能再次杀死该玩家。                                                                                                  |
| language                                      | 字符串     | 将使用 /lang/ 文件夹中的哪个文件作为管理文本。例如,值为"FR-fr"将导致加载"/lang/FR-fr/strings.yml"。                                                          |
| language-override-client                      | true/false | `language`设置是否应在发送所有类型的文本时覆盖客户端语言。                                                                                                    |
| max-quests                                    | 数字       | 任何给定玩家可以拥有的最大任务数量。                                                                                                                          |
| npc-effects.enabled                           | true/false | 是否启用粒子效果。请注意,客户端必须启用粒子。                                                                                                                  |
| npc-effects.new-quest                         | 字符串     | 为新任务播放的粒子效果(例如 note, enchant, crit, spell, portal)。                                                                                              |
| npc-effects.redo-quest                        | 字符串     | 为可重复任务播放的粒子效果(例如 note, enchant, crit, spell, portal)。                                                                                          |
| prevent-exploit                               | true/false | 尝试防止适用任务中的背包漏洞。                                                                                                                               |
| show-requirements                             | true/false | 允许玩家在 /quest \[quest] 中查看要求                                                                                                                         |
| show-titles                                   | true/false | 在接受/完成任务时向玩家显示标题。                                                                                                                            |
| strict-player-movement                        | 数字       | 高级玩家移动跟踪之间的秒数。                                                                                                                                  |
| storage-data.address                          | 字符串     | 可选存储的IP地址。                                                                                                                                            |
| storage-data.database                         | 字符串     | 可选存储的表名。                                                                                                                                              |
| storage-data.username                         | 字符串     | 可选存储的登录用户名。                                                                                                                                        |
| storage-data.password                         | 字符串     | 可选存储的登录密码。                                                                                                                                          |
| storage-data.pool-settings.max-pool-size      | 数字       | 高级HikariCP设置。                                                                                                                                            |
| storage-data.pool-settings.min-idle           | 数字       | 高级HikariCP设置。                                                                                                                                            |
| storage-data.pool-settings.max-lifetime       | 数字       | 高级HikariCP设置。                                                                                                                                            |
| storage-data.pool-settings.connection-timeout | 数字       | 高级HikariCP设置。                                                                                                                                            |
| storage-method.player-data                    | 字符串     | yaml = 文件存储, mysql = 远程存储, custom = 开发者存储                                                                                                         |
| top-limit                                     | 数字       | /quests top \[number] 可以显示的最大任务数量                                                                                                                  |
| translate-names                               | true/false | 将物品/生物名称翻译为客户端的游戏语言。                                                                                                                         |
| translate-subcommands                         | true/false | 将子命令翻译为服务器的插件语言。                                                                                                                              |
| trial-save                                    | true/false | 允许在试用模式下保存。                                                                                                                                        |
| update-check                                  | true/false | 是否允许检查插件更新。                                                                                                                                        |

### actions.yml

{% hint style="info" %}
不建议手动编辑此文件。对于选择不使用游戏内编辑器的人,将不提供支持。
{% endhint %}

此文件保存执行某些任务和效果的动作。除包含的示例外,动作在任务中使用之前创建。这最好通过 _/quests actions_ 命令完成。

> [点击此处查看默认的actions.yml文件。](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/actions.yml)

### conditions.yml

{% hint style="info" %}
不建议手动编辑此文件。对于选择不使用游戏内编辑器的人,将不提供支持。
{% endhint %}

此文件保存在游戏期间检查的条件。除包含的示例外,条件在任务中使用之前创建。这最好通过 _/quests conditions_ 命令完成。

> [点击此处查看默认的conditions.yml文件。](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/conditions.yml)

### quests.yml

{% hint style="info" %}
不建议手动编辑此文件。对于选择不使用游戏内编辑器的人,将不提供支持。
{% endhint %}

此文件包含所有保存的任务。包含一些示例任务,您可以随时删除。这最好通过 _/quests editor_ 命令完成。

> [点击此处查看默认的quests.yml文件。](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/quests.yml)

