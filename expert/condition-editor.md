# Condition Editor

When a player is carrying out a stage of a quest, it may be desirable to force them to meet a certain criteria. For example, holding a specific item while completing objectives. To do this, a condition must be created and applied.

To make a condition, run **/quests conditions** in-game (or from the console, with limited features). You will be greeted with the following:

![](../.gitbook/assets/condition\_editor.png)

Enter '1' in chat so the plugin may prompt you to enter a name for your condition. This can be any alphanumeric sequence, which means letters and numbers are OK, but no special characters or symbols! Don't worry, you can change it later if you're unsure.

After you've chosen a valid name, this screen will appear:

![](../.gitbook/assets/condition\_main.png)

<details>

<summary>Expand to see the breakdown.</summary>

1. Change the name of your condition
2. Ride an entity or [Citizens](https://pikamug.gitbook.io/quests/v/spanish-espanol/beginner/dependencies#citizens) NPC
3. Own permission, hold item in main hand, or wear items as armor
4. Stay within world, stay within ticks, stay within biome, or stay within [WorldGuard](https://pikamug.gitbook.io/quests/v/spanish-espanol/beginner/dependencies#citizens) region
5. Whether placeholder value is true
6. Whether to fail quest if condition not met
7. Finish working on your condition
8. Discard all work on your condition

</details>

Select a condition type and decide whether the player should fail the quest if said condition is not met. Now, enter all the appropriate prompt numbers for 'Done' until you've saved your condition.

Nice job! Unlike the [Quest Editor](../setup/quests-editor.md), there is no need to reload the plugin. Exit the Condition Editor and then create or edit a quest in the Quest Editor. Go to the 'Edit Stages' menu and, after setting at least one objective, select option 11 to apply the condition.
