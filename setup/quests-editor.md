# Quest Editor

Let's make a quest! By default, the Quest Editor is available only to server ops. However, with the [correct permissions](https://pikamug.gitbook.io/quests/setup/commands-and-permissions) in place, it's as simple as running **/quests editor** in-game (or from the console, with limited features). You will be greeted with the following:

![](../.gitbook/assets/quest\_editor.png)

Enter '1' in chat so the plugin may prompt you to enter a name for your quest. This can be any alphanumeric sequence, which means letters and numbers are OK, but no special characters or symbols! Don't worry, you can change it later if you're unsure.

After you've chosen a valid name, this screen will appear:

![](../.gitbook/assets/quest\_main.png)

<details>

<summary>Expand to see the breakdown.</summary>

1. Change the name of your quest
2. Shown to player when accepting quest
3. Shown to player after completing quest
4. Must speak to this [Citizens](https://pikamug.gitbook.io/quests/beginner/dependencies#citizens) or [ZNPCsPlus](https://pikamug.gitbook.io/quests/beginner/dependencies#znpcsplus) NPC to start quest
5. Must right-click on this block to start quest
6. Must stand in this [WorldGuard](https://pikamug.gitbook.io/quests/beginner/dependencies#worldguard) region to start quest
7. Use NPC GUI to start quest instead of chat
8. Change what a player needs to take your quest
9. Change the time(s) that your quest is available
10. Change what objectives your quest consists of
11. Change what a player gets for taking your quest
12. Change settings purely specific to your quest
13. Finish working on your quest
14. Discard all work on your quest

</details>

That's a lot of choices! Enter '2' and then input the first thing you'd like the player to hear for your quest. Once you're done, enter '3' to input the final message to come from your quest.

{% hint style="info" %}
**Pro-tip:** If you have [Citizens 2](https://www.spigotmc.org/resources/citizens.13811/) installed for NPCs, you may enter '4' to select an NPC that you'd like to hand out the quest.
{% endhint %}

Great job! Now, if you go to save your quest, you'll get an error. This is because all quests must contain at least one stage. So, let's create one! Enter '11' to begin, then '1' to add your first stage.

![](../.gitbook/assets/quest\_stage.png)

<details>

<summary>Expand to see the breakdown.</summary>

1. Includes objectives to break, place, damage, or use blocks
2. Includes objectives to craft, smelt, or enchant items
3. Includes objectives to deliver items to, talk to, or kill NPCs
4. Includes objectives to kill or tame mobs, catch fish, or shear sheep
5. Objective to kill an amount of players
6. Objective to travel to a specific radius of world coordinates
7. Objective to enter a specific string in chat
8. Objective from an installed [custom module](../casual/modules.md)
9. After setting at least one objective, run an [action](../casual/action-editor.md) at the start, end, or during the stage
10. After setting at least one objective, check a [condition](../expert/condition-editor.md) during the stage
11. Number of seconds to wait before the next stage may begin
12. After setting a delay, show a message to the player once the delay starts
13. Show a message to the player once the stage begins
14. Show a message to the player once the stage ends
15. Override the message shown to the player about what their objectives are
16. Permanently remove this stage
17. Finish working on your stage

</details>

Behold the magic of Quests! There are so many different objectives to choose from that the possibilities seem endless! Let's try a basic quest to break some blocks. Enter '1' to continue to the Blocks menu, then '1' again to select Break blocks.

{% hint style="info" %}
**Pro-tip:** Custom objectives come from special add-ons which often link with other plugins, found [here](https://pikamug.gitbook.io/quests/casual/modules). To use one, it must be installed in your /Quests/modules folder at startup.
{% endhint %}

![](../.gitbook/assets/quest\_break.png)

Here, you can enter whichever block you would like the player to break. Dirt makes for an easy challenge, so let's have the player break five of them. If you're using a Minecraft version _older_ than 1.13, you can also set durability to use block variants (for example, a value of '3' would equate to Podzol rather than Dirt).

{% hint style="info" %}
**Pro-tip:** Players may break blocks without affecting the quest by using a pickaxe with the Silk Touch enchantment. This feature can be disabled in [Options](../beginner/options.md).
{% endhint %}

Enter all the appropriate prompt numbers for 'Done' until you're back at the ask/finish message screen. You're nearly finished! Enter '13' and then '1' to save your quest.

Great work! To give your new quest a try, either run **/questadmin reload** or restart the server (do _not_ use /reload) and then **/quests take \[yourQuestName]**. Once you make a few more, you should share your most interesting quest lines on [our Discord](https://discordapp.com/invite/d56CQ6e). Have fun!
