# Quest Editor

Let's make a quest! By default, the Quest Editor is available only to server ops. However, with the [correct permissions](https://pikamug.gitbook.io/quests/setup/commands-and-permissions) in place, it's as simple as running **/quests editor** in-game (or from the console, with limited features). You will be greeted with the following:

![](https://camo.githubusercontent.com/fd0571c9f8dd71b0cdcd37522e00efd6841fb861d9c74cc0f0936b5688ba6f39/68747470733a2f2f692e696d6775722e636f6d2f35664c645170612e706e67)

Enter '1' in chat so the plugin may prompt you to enter a name for your quest. This can be any alphanumeric sequence, which means letters and numbers are OK, but no special characters or symbols! Don't worry, you can change it later if you're unsure.

After you've chosen a valid name, this screen will appear:

![](https://camo.githubusercontent.com/fda7a8693ba61b3a030bccc4911a806db2346282c26833a2d3d9195be39f2641/68747470733a2f2f692e696d6775722e636f6d2f4865473977394b2e706e67)

That's a lot of choices! Enter '2' and then input the first thing you'd like the player to hear for your quest. Once you're done, enter '3' to input the final message to come from your quest.

{% hint style="info" %}
**Pro-tip:** If you have [Citizens 2](https://www.spigotmc.org/resources/citizens.13811/) installed for NPCs, you may enter '4' to select an NPC that you'd like to hand out the quest.
{% endhint %}

Great job! Now, if you go to save your quest, you'll get an error. This is because all quests must contain at least one stage. So, let's create one! Enter '11' to begin, then '1' to add your first stage.

![](https://camo.githubusercontent.com/9065d04debad1a0a95a37fc3baa6518478dd7d4989d3abd63773f7b8c6a385ea/68747470733a2f2f692e696d6775722e636f6d2f61556562344a512e706e67)

Behold the magic of Quests! There are so many different objectives to choose from that the possibilities seem endless! Let's try a basic quest to break some blocks. Enter '1' to continue to the Blocks menu, then '1' again to select Break blocks.

{% hint style="info" %}
**Pro-tip:** Custom objectives come from special add-ons which often link with other plugins, found [here](https://pikamug.gitbook.io/quests/casual/modules). To use one, it must be installed in your /Quests/modules folder at startup.
{% endhint %}

![](https://camo.githubusercontent.com/e30adfdd454a751bb6ac89e116223d44731c9ecb7939bbe0438de6ecbb2da2c4/68747470733a2f2f692e696d6775722e636f6d2f393267764744492e706e67)

Here, you can enter whichever block you would like the player to break. Dirt makes for an easy challenge, so let's have the player break five of them. If you're using a Minecraft version _older_ than 1.13, you can also set durability to use block variants (for example, a value of '3' would equate to Podzol rather than Dirt).

{% hint style="info" %}
**Pro-tip:** Players may break blocks without affecting the quest by using a pickaxe with the Silk Touch enchantment. This feature can be disabled in [Options](../beginner/options.md).
{% endhint %}

Enter all the appropriate prompt numbers for 'Done' until you're back at the ask/finish message screen. You're nearly finished! Enter '13' and then '1' to save your quest.

Great work! To give your new quest a try, either run **/questadmin reload** or restart the server (do _not_ use /reload) and then **/quests take \[yourQuestName]**. Once you make a few more, you should share your most interesting quest lines on [our Discord](https://discordapp.com/invite/d56CQ6e). Have fun!
