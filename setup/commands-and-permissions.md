# 命令与权限

Quests 的三个主要命令是 **/quests**、**/quest** 和 **/questadmin**。前两个命令默认对所有玩家开放，最后一个命令则专供服务器管理员使用。要更改此行为（例如将 **/questadmin** 授予非管理员玩家），您需要设置[权限](https://bukkit.gamepedia.com/Understanding_Permissions)。

### 玩家命令

下表描述了每个命令及其关联权限。请注意，子命令（list、take、quit 等）可能会因您[选择其他插件语言](../casual/translations.md)而发生变化，但权限节点将保持不变。

| 命令                          | 权限节点          | 描述                             |
| ----------------------------- | ----------------- | -------------------------------- |
| /quests                       | quests.quests     | 显示插件帮助信息                 |
| /quests list \[page]          | quests.list       | 列出可用任务                     |
| /quests take \[quest]         | quests.take       | 通过命令接受任务                 |
| /quests quit \[quest]         | quests.quit       | 放弃当前任务                     |
| /quests stats                 | quests.stats      | 查看任务统计信息                 |
| /quests top \[number]         | quests.top        | 查看插件排行榜                   |
| /quests info                  | quests.info       | 查看插件信息                     |
| /quests journal               | quests.journal    | 切换任务日志                     |
| N/A                           | quests.compass    | 使用指南针追踪任务               |
| N/A                           | quests.choice     | 使用可点击文本                   |
|                               |                   |                                  |
| /quest                        | quests.quest      | 查看当前任务目标                 |
| /quest \[quest]               | quests.questinfo  | 查看某个任务的信息               |

{% hint style="info" %}
**小贴士：** 默认情况下，您也可以分别使用 **/qs** 和 **/q** 来代替 **/quests** 和 **/quest**！
{% endhint %}

### 管理员命令

管理员命令仅应授予您信任不会滥用的人员，下表列出了这些命令。

| 命令                                             | 权限节点                   | 描述                                       |
| ------------------------------------------------ | -------------------------- | ------------------------------------------ |
| /questadmin                                      | quests.admin               | 显示管理员帮助信息                         |
| /questadmin stats \[player]                      | quests.admin.stats         | 查看某玩家的任务统计信息                   |
| /questadmin give \[player] \[quest]              | quests.admin.give          | 强制某玩家接受任务                         |
| /questadmin quit \[player] \[quest]              | quests.admin.quit          | 强制某玩家放弃任务                         |
| /questadmin points \[player] \[amount]           | quests.admin.points        | 设置某玩家的任务点数                       |
| /questadmin takepoints \[player] \[amount]       | quests.admin.takepoints    | 扣除某玩家的任务点数                       |
| /questadmin givepoints \[player] \[amount]       | quests.admin.givepoints    | 增加某玩家的任务点数                       |
| /questadmin finish \[player] \[quest]            | quests.admin.finish        | 强制某玩家完成任务                         |
| /questadmin nextstage \[player] \[quest]         | quests.admin.nextstage     | 强制某玩家完成当前阶段                     |
| /questadmin setstage \[player] \[quest] \[stage] | quests.admin.setstage      | 为某玩家设置当前任务阶段                   |
| /questadmin reset \[player]                      | quests.admin.reset         | 清除某玩家的所有任务数据                   |
| /questadmin remove \[player] \[quest]            | quests.admin.remove        | 从某玩家记录中移除已完成的任务             |
| /questadmin reload                               | quests.admin.reload        | 安全地重新加载插件                         |
| N/A                                              | quests.admin.drop          | 允许丢弃任务日志                           |
| N/A                                              | quests.admin.update        | 查看插件更新通知                           |
| N/A                                              | quests.mode.trial          | 有限访问编辑器，默认禁用                   |
| /quests editor                                   | quests.editor.editor       | 打开任务编辑器                             |
| N/A                                              | quests.editor.create       | 创建新任务                                 |
| N/A                                              | quests.editor.edit         | 编辑现有任务                               |
| N/A                                              | quests.editor.delete       | 删除现有任务                               |
| /quests actions                                  | quests.actions.editor      | 打开动作编辑器                             |
| N/A                                              | quests.actions.create      | 创建新动作                                 |
| N/A                                              | quests.actions.edit        | 编辑现有动作                               |
| N/A                                              | quests.actions.delete      | 删除现有动作                               |
| /quests conditions                               | quests.conditions.editor   | 打开条件编辑器                             |
| N/A                                              | quests.conditions.create   | 创建新条件                                 |
| N/A                                              | quests.conditions.edit     | 编辑现有条件                               |
| N/A                                              | quests.conditions.delete   | 删除现有条件                               |

{% hint style="info" %}
**小贴士：** 使用 _quests.admin.\*_, _quests.editor.\*_, _quests.actions.\*_ 和 _quests.conditions.\*_ 可以分别涵盖所有管理员和编辑器权限！默认情况下，您也可以使用 **/qa** 来代替 **/questadmin**！
{% endhint %}