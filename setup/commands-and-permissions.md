# Commands & Permissions

The three main commands for Quests are **/quests**, **/quest**, and **/questadmin**. The first two are enabled for all users by default, while the last one is reserved for server ops. To change this behavior, such as giving **/questadmin** to non-op administrators, you must set up [permissions](https://bukkit.gamepedia.com/Understanding_Permissions).

### Player Commands

Below is a chart which describes each command and its associated permission. Note that the subcommands \(list, take, quit, et al.\) can change if you [select another plugin language](https://github.com/PikaMug/Quests/wiki/Translations), but permissions will remain the same.

| Command | Permission | Description |
| :--- | :--- | :--- |
| /quests | quests.quests | Display plugin help |
| /quests list \[page\] | quests.list | List available quests |
| /quests take \[quest\] | quests.take | Accept a quest via command |
| /quests quit \[quest\] | quests.quit | Quit a current quest |
| /quests stats | quests.stats | View quest statistics |
| /quests top \[number\] | quests.top | View plugin leaderboards |
| /quests info | quests.info | View plugin information |
| /quests journal | quests.journal | Toggle the Quest Journal |
| N/A | quests.compass | Track quests using a Compass |
|  |  |  |
| /quest | quests.quest | View current quest objectives |
| /quest \[quest\] | quests.questinfo | View information about a quest |

{% hint style="info" %}
**Pro-tip:** By default, you can also use **/qs** and **/q** in place of **/quests** and **/quest**, respectively!
{% endhint %}

### Administrator Commands

Administrator commands, which should only be granted to those you trust not to misuse them, are outlined below.

| Command | Permission | Description |
| :--- | :--- | :--- |
| /questadmin | quests.admin | Display administrator help |
| /questadmin stats \[player\] | quests.admin.stats | View quest statistics of a player |
| /questadmin give \[player\] \[quest\] | quests.admin.give | Force a player to take a quest |
| /questadmin quit \[player\] \[quest\] | quests.admin.quit | Force a player to quit a quest |
| /questadmin points \[player\] \[amount\] | quests.admin.points | Set a player's Quest Points |
| /questadmin takepoints \[player\] \[amount\] | quests.admin.takepoints | Take away a player's Quest Points |
| /questadmin givepoints \[player\] \[amount\] | quests.admin.givepoints | Add to a player's Quest Points |
| /questadmin pointsall \[player\] \[amount\] | quests.admin.pointsall | Set ALL players' Quest Points |
| /questadmin finish \[player\] \[quest\] | quests.admin.finish | Force a player to complete a quest |
| /questadmin nextstage \[player\] \[quest\] | quests.admin.nextstage | Force a player to complete current stage |
| /questadmin setstage \[player\] \[quest\] \[stage\] | quests.admin.setstage | Set the current stage for a player |
| /questadmin reset \[player\] | quests.admin.reset | Clear all Quests data of a player |
| /questadmin remove \[player\] \[quest\] | quests.admin.remove | Remove a completed quest from a player |
| /questadmin reload | quests.admin.reload | Safely reload the plugin |
| N/A | quests.admin.drop | Ability to drop the Quests Journal |
| N/A | quests.admin.trial | Limited access to editors, disabled by default |
| /quests editor | quests.editor.editor | Ability to open Quests Editor |
| N/A | quests.editor.create | Ability to create new quests |
| N/A | quests.editor.edit | Ability to edit existing quests |
| N/A | quests.editor.delete | Ability to delete existing quests |
| /quests actions | quests.actions.editor | Ability to open Action Editor |
| N/A | quests.actions.create | Ability to create new actions |
| N/A | quests.actions.edit | Ability to edit existing actions |
| N/A | quests.actions.delete | Ability to delete existing actions |
| /quests conditions | quests.conditions.editor | Ability to open Condition Editor |
| N/A | quests.conditions.create | Ability to create new conditions |
| N/A | quests.conditions.edit | Ability to edit existing conditions |
| N/A | quests.conditions.delete | Ability to delete existing conditions |

{% hint style="info" %}
**Pro-tip:** Use _quests.admin.\*_, _quests.editor.\*_, _quests.actions.\*_ and _quests.conditions.\*_ to encompass all admin and editor permissions, respectively! By default, you can also use **/qa** instead of **/questadmin**!
{% endhint %}

### Legacy Commands

The following commands have either been removed from or altered within Quests:

| Command | Permission | Description |
| :--- | :--- | :--- |
| /questadmin togglegui \[npc id\] | quests.admin.togglegui | Toggle GUI Quest Display on an NPC _\(Removed in Quests 3.8.0\)_ |

### Legacy Permissions

Those using Quests 3.4.7 or older must instead use the "Old" permissions for the Events Editor, [as shown here](https://pastebin.com/tcYBebK5). Anyone using Quests 3.4.8 to 3.6.9 should use the "New" permission from that same link.



