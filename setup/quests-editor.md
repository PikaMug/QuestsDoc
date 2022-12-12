# Quest Editor

Let's make a quest! By default, the Quest Editor is available only to server ops. However, with the [correct permissions](https://github.com/PikaMug/Quests/wiki/1-%E2%80%90-Commands-&-Permissions) in place, it's as simple as running **/quests editor** in-game (or from the console, with limited features). You will be greeted with the following:

![](../.gitbook/assets/quest\_editor.png)

Enter '1' in chat so the plugin may prompt you to enter a name for your quest. This can be any alphanumeric sequence, which means letters and numbers are OK, but no special characters or symbols! Don't worry, you can change it later if you're unsure.

After you've chosen a valid name, this screen will appear:

![](../.gitbook/assets/quest\_main.png)

That's a lot of choices! Enter '2' and then input the first thing you'd like the player to hear for your quest. Once you're done, enter '3' to input the final message to come from your quest.

{% hint style="info" %}
**Pro-tip:** If you have [Citizens 2](https://www.spigotmc.org/resources/citizens.13811/) installed for NPCs, you may enter '4' to select an NPC that you'd like to hand out the quest.
{% endhint %}

Great job! Now, if you go to save your quest, you'll get an error. This is because all quests must contain at least one stage. So, let's create one! Enter '11' to begin, then '1' to add your first stage.

![](../.gitbook/assets/quest\_stage.png)

Behold the magic of Quests! There are so many different objectives to choose from that the possibilities seem endless! Let's try a basic quest to break some blocks. Enter '1' to continue to the Blocks menu, then '1' again to select Break blocks.

{% hint style="info" %}
**Pro-tip:** Custom objectives come from special add-ons which often link with other plugins, found [here](https://github.com/PikaMug/Quests/wiki/Casual-%E2%80%90-Modules). To use one, it must be installed in your /Quests/modules folder at startup.
{% endhint %}

![](../.gitbook/assets/quest\_break.png)

Here, you can enter whichever block you would like the player to break. Dirt makes for an easy challenge, so let's have the player break five of them. If you're using a Minecraft version _older_ than 1.13, you can also set durability to use block variants (for example, a value of '3' would equate to Podzol rather than Dirt).

{% hint style="info" %}
**Pro-tip:** Players may break blocks without affecting the quest by using a pickaxe with the Silk Touch enchantment. This feature can be disabled in [Options](../beginner/options.md).
{% endhint %}

Enter all the appropriate prompt numbers for 'Done' until you're back at the ask/finish message screen. You're nearly finished! Enter '13' and then '1' to save your quest.

Great work! To give your new quest a try, either run **/questadmin reload** or restart the server (do _not_ use /reload) and then **/quests take \[yourQuestName]**. Once you make a few more, you should share your most interesting quest lines on [our Discord](https://discordapp.com/invite/d56CQ6e). Have fun!
