# Action Editor

{% hint style="info" %}
**Notice:** This information is intended for intermediate users. Read carefully!
{% endhint %}

Similar to how all quest stages have objectives, they can also perform actions. An action is something that happens during a stage, but is typically cosmetic and doesn't inherently progress the quest. For example, causing a player to lose hunger or get struck by lightning are considered actions.

To make an action, run **/quests actions** in-game (it is not currently accessible from the console). You will be greeted with the following:

![](https://camo.githubusercontent.com/e8b5f6ac7b8f17ac0aae2f247c7fe7b2b20c877082c6f2e98f96cc3533753b3f/68747470733a2f2f692e696d6775722e636f6d2f7452474e4e65752e706e67)

Enter '1' in chat so the plugin may prompt you to enter a name for your action. This can be any alphanumeric sequence, which means letters and numbers are OK, but no special characters or symbols! Don't worry, you can change it later if you're unsure.

![](https://camo.githubusercontent.com/142258f62b59f0a4536534206b216dd96f26bb14e4805851fd4ecc45d96d2490/68747470733a2f2f692e696d6775722e636f6d2f7877307a6753752e706e67)

After you've chosen a valid name, this screen will appear:

![](https://camo.githubusercontent.com/6c685a9d56578d14d1cda1edc55b64b92e35f67b4c94d848835a94b774ff76fe/68747470733a2f2f692e696d6775722e636f6d2f7572756d6a69712e706e67)

For now, enter '5' for the Weather menu, then '2' to set up an action which will force thunder across a world for a while.

![](https://camo.githubusercontent.com/940111094d4d4d9b3f88d94f0b5c847b6752e564c9fee6f243d97853e1d698fd/68747470733a2f2f692e696d6775722e636f6d2f615453536552542e706e67)

Input '1' to select one of your Minecraft server's worlds by name. They will be listed for your convenience, but you can only select one! You may create a second action later if you wish to deal out thunder across multiple worlds.

Once that's done, enter '2' to set a duration of time in seconds. This is how long your thunder action will last for. As an example, type in 180 for the event to last 3 minutes.

Enter all the appropriate prompt numbers for 'Done' until you've saved your action! You should be greeted with this message:

![](https://camo.githubusercontent.com/1c753f790d3139529192b019783428d8ed6e9eb9b2665f0c1af90cd144e1be07/68747470733a2f2f692e696d6775722e636f6d2f59496f496172512e706e67)

Nice job! Unlike the [Quest Editor](../setup/quests-editor.md), there is no need to reload the plugin. Exit the Action Editor and then create or edit a quest in the Quest Editor. Go to the 'Edit Stages' menu and, after setting at least one objective, select option 9 to run the action before, during, or after the stage:

![](https://camo.githubusercontent.com/ea5fd196915be6fa887d780bb5f0a42f439f336960cda2f550efc998c1621b24/68747470733a2f2f692e696d6775722e636f6d2f4e6a48476979352e706e67)

Chat and command actions are run during the stage when the player enters a specific keyword or command in-game, respectively.
