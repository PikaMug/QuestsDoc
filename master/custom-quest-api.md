# Custom Quest API

{% hint style="info" %}
**Alert:** This information is intended for developers. Learn how to use Java first!
{% endhint %}

### Add to your project

If you're using Maven or another project management tool, add the latest version of Quests using [Jitpack](https://jitpack.io/#PikaMug/Quests).

### Learn the interface

Quests provides a simple API to create custom requirements, rewards, and objectives. To begin, make sure you are compiling against version 4.0.0 or above. Once you've finished following this guide, use the /Quests/modules folder as the destination for your finished and compiled jar. If distributing your module, make sure to inform the end user of the correct folder location.Click here for legacy information

#### Requirements API

Building a Quests Requirement is very simple. To get started, create a Java class that extends the CustomRequirement class. After that, check out this example of a Custom Requirement where the player must have a particular name in order to take the Quest:

```java
package xyz.janedoe;

import java.util.Map;
import org.bukkit.entity.Player;
import me.blackvein.quests.CustomRequirement;

public class NameRequirement extends CustomRequirement {
    // Construct the requirement
    public NameRequirement() {
        this.setName("Name Requirement");
        this.setAuthor("Jane Doe");
        this.addItem("NAME_TAG", 0);
        this.addStringPrompt("Name", "Enter value that player's name must contain in order to take the Quest", null);
        this.addStringPrompt("Case-Sensitive", "Should the check be case-sensitive or not? (Enter \'true\' or \'false\'", null);
	this.setDisplay("Sorry, you are not on the list.");
    }
    
    // Test whether a player has met the requirement
    @Override
    public boolean testRequirement(Player player, Map<String, Object> data) {
	      String caseSensitive = (String) data.get("Case-Sensitive");
		
	      // Check whether the name must be case-sensitive
	      if (caseSensitive.equalsIgnoreCase("true")) {
	          // Mark the requirement as satisfied if name matches
	          return player.getName().contains((String)data.get("Name"));
	      } else {
	          // Mark the requirement as satisfied if name matches, ignoring case
	          return player.getName().toLowerCase().contains(((String)data.get("Name")).toLowerCase());
	      }
    }
}
```

In the constructor of your class, you may use any of the following methods:

| Method | Description |
| :--- | :--- |
| setName | Sets the name of the Custom Objective. |
| setAuthor | Sets the author of the Custom Objective \(you!\). |
| addItem | Add an item which might appear in overlay plugins like QuestsGUI. |
| setDisplay | Sets how the requirement is displayed when failed. |
| addStringPrompt | Adds a new editor prompt with the specified title, description, and default value for your Custom Objective. Quest editors may input a string which is up to you to parse. |

Inside \#testRequirement is where you perform your logic to determine whether the player passes the requirement, returning true if they do, and false if they do not.

The data Map contains the data that the person who created the Quest gave to it. In this example, the data Map contains the two values for 'Name' and 'Case-Sensitive'. Also, note that while the values are of type Object, they were cast to type String internally. You must perform manual type-conversion if you want to obtain integers, booleans, et al.

#### Rewards API

Building a Quests Reward is very simple. To get started, create a Java class that extends the CustomReward class. After that, check out this example of a Custom Reward where a player gets a GUI Inventory that pops up containing iron, gold and diamonds:

```java
package xyz.janedoe;

import java.util.Map;

import org.bukkit.Bukkit;
import org.bukkit.Material;
import org.bukkit.entity.Player;
import org.bukkit.inventory.Inventory;
import org.bukkit.inventory.ItemStack;

import me.blackvein.quests.CustomReward;

public class LootReward extends CustomReward {
    // Construct the reward
    public LootReward() {
        this.setName("Loot Reward");
        this.setAuthor("Jane Doe");
        this.addItem("CHEST", 0);
        this.setRewardName("Loot Chest: %Title%");
        this.addStringPrompt("Title", "Title of the loot inventory interface.", null);
        this.addStringPrompt("NumIron", "Enter the number of iron ingots to give in the loot chest.", null);
        this.addStringPrompt("NumGold", "Enter the number of gold ingots to give in the loot chest.", null);
        this.addStringPrompt("NumDiamond", "Enter the number of diamonds to give in the loot chest.", null);
    }
    
    // Give loot reward to a player
    @Override
    public void giveReward(Player player, Map<String, Object> data) {
        String title = (String) data.get("Title");
        int numIron = 0;
        int numGold = 0;
        int numDiamond = 0;
        
        // Attempt to load user input as integers
        try {
            numIron = Integer.parseInt((String) data.get("NumIron"));
        } catch (NumberFormatException nfe) {
        	Bukkit.getLogger().severe("Loot Reward has invalid Iron number: " + numIron);
        }
        try {
            numGold = Integer.parseInt((String) data.get("NumGold"));
        } catch (NumberFormatException nfe) {
        	Bukkit.getLogger().severe("Loot Reward has invalid Gold number: " + numGold);
        }
        try {
            numDiamond = Integer.parseInt((String) data.get("NumDiamond"));
        } catch (NumberFormatException nfe) {
        	Bukkit.getLogger().severe("Loot Reward has invalid Diamond number: " + numDiamond);
        }
        
        // Create a temporary inventory to add items to
        Inventory inv = Bukkit.getServer().createInventory(player, 3, title);
        int slot = 0;

        // Check if amount is greater than default value
        if (numIron > 0) {
            // Add item to current slot in temporary inventory, then get next slot ready
            inv.setItem(slot, new ItemStack(Material.IRON_INGOT, numIron > 64 ? 64 : numIron));
            slot++;
        }
        if (numGold > 0) {
            inv.setItem(slot, new ItemStack(Material.GOLD_INGOT, numGold > 64 ? 64 : numGold));
            slot++;
        }
        if (numDiamond > 0) {
            inv.setItem(slot, new ItemStack(Material.DIAMOND, numDiamond > 64 ? 64 : numDiamond));
        }
        
        // Open temporary inventory for player to accept items
        player.openInventory(inv);
    }
}
```

In the constructor of your class, you may use any of the following methods:

| Method | Description |
| :--- | :--- |
| setName | Sets the name of the Custom Objective. |
| setAuthor | Sets the author of the Custom Objective \(you!\). |
| addItem | Add an item which might appear in overlay plugins like QuestsGUI. |
| setRewardName | Sets the reward name \(text that will appear when the player completes the Quest\) of the Custom Reward. |
| addStringPrompt | Adds a new editor prompt with the specified title, description, and default value for your Custom Objective. Quest editors may input a string which is up to you to parse. |

Inside \#giveReward is where you perform your logic to give the player whatever it is your Custom Reward gives. The data Map contains the data that the person who created the Quest gave to it. In this example, the data Map contains four values: One for the title of the GUI, and three for the amount of iron/gold/diamonds. Also, note that while the values are of type Object, they were cast to type String internally. You must perform manual type-conversion if you want to obtain integers, booleans, et al.

#### Objectives API

Building a Quests Objective is a bit more complicated than Requirements or Rewards. To get started, create a Java class that extends the CustomObjective class. If you want to catch one of Bukkit's Events, you'll need to implement the Listener class \(Quests will take care of registering it for you\). After that, check out these examples of a Custom Objective:

{% tabs %}
{% tab title="Example 1" %}
```java
// Player must gain a certain amount of experience to advance

package xyz.janedoe;

import me.blackvein.quests.CustomObjective;
import me.blackvein.quests.Quest;
import me.blackvein.quests.Quests;

import org.bukkit.Bukkit;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.event.player.PlayerExpChangeEvent;

public class ExperienceObjective extends CustomObjective implements Listener {
    // Get the Quests plugin
    Quests qp = (Quests)Bukkit.getServer().getPluginManager().getPlugin("Quests");
	
    // Construct the objective
    public ExperienceObjective() {
        this.setName("Experience Objective");
        this.setAuthor("Jane Doe");
        this.addItem("BOOK", 0);
        this.setShowCount(true);
        this.setCountPrompt("Enter the experience points that the player must acquire:");
        this.setDisplay("Acquire experience points: %count%");
    }

    // Catch the Bukkit event for a player gaining/losing exp
    @EventHandler
    public void onPlayerExpChange(PlayerExpChangeEvent evt) {
        // Make sure to evaluate for all of the player's current quests
        for (Quest quest : qp.getQuester(evt.getPlayer().getUniqueId()).getCurrentQuests().keySet()) {
            // Check if the player gained exp, rather than lost
            if (evt.getAmount() > 0) {
                // Add to the objective's progress, completing it if requirements were met
                incrementObjective(evt.getPlayer(), this, evt.getAmount(), quest);
            }
        }
    }
}
```
{% endtab %}

{% tab title="Example 2" %}
```java
// Require the player to drop a certain number of a certain type of item.

package xyz.janedoe;

import me.blackvein.quests.CustomObjective;
import me.blackvein.quests.Quest;
import me.blackvein.quests.Quests;

import org.bukkit.Bukkit;
import org.bukkit.entity.EntityType;
import org.bukkit.event.EventHandler;
import org.bukkit.event.player.PlayerDropItemEvent;
import org.bukkit.inventory.ItemStack;

public class DropItemObjective extends CustomObjective {
    // Get the Quests plugin
    Quests qp = (Quests)Bukkit.getServer().getPluginManager().getPlugin("Quests");

    // Construct the objective
    public DropItemObjective() {
        this.setName("Drop Item Objective");
        this.setAuthor("Jane Doe");
        this.addItem("ANVIL", 0);
        this.setShowCount(true);
        this.setCountPrompt("Enter the amount that the player must drop:");
        this.setDisplay("Drop %Item Name%: %count%");
        this.addStringPrompt("Item Name", "Enter the name of the item that the player must drop", "DIRT");
    }

    // Catch the Bukkit event for a player dropping an item
    @EventHandler
    public void onPlayerDropItem(PlayerDropItemEvent evt){
    	// Make sure to evaluate for all of the player's current quests
    	for (Quest quest : qp.getQuester(evt.getPlayer().getUniqueId()).getCurrentQuests().keySet()) {
    	    Map<String, Object> map = getDataForPlayer(evt.getPlayer(), this, quest);
	    if (map == null) {
	        continue;
            }
            ItemStack stack = evt.getItemDrop().getItemStack();
            String userInput = (String) map.get("Item Name");
            EntityType type = EntityType.fromName(userInput);
            // Display error if user-specified item name is invalid
            if (type == null) {
            	Bukkit.getLogger().severe("Drop Item Objective has invalid item name: " + userInput);
            	continue;
            }
            // Check if the item the player dropped is the one user specified
            if (evt.getItemDrop().getItemStack().getType().equals(type)) {
    		// Add to the objective's progress, completing it if requirements were met
            	incrementObjective(evt.getPlayer(), this, stack.getAmount(), quest);
            }
    	}
    }
}
```
{% endtab %}

{% tab title="Example 3" %}
```java
// Allow player to break ANY block rather than a specific one

package xyz.janedoe;

import me.blackvein.quests.CustomObjective;
import me.blackvein.quests.Quest;
import me.blackvein.quests.Quests;

import org.bukkit.Bukkit;
import org.bukkit.entity.Player;
import org.bukkit.event.EventHandler;
import org.bukkit.event.EventPriority;
import org.bukkit.event.block.BlockBreakEvent;

public class AnyBreakBlockObjective extends CustomObjective {
    // Get the Quests plugin
    private static Quests quests = (Quests) Bukkit.getServer().getPluginManager().getPlugin("Quests");
    
    public AnyBreakBlockObjective() {
        setName("Break Blocks Objective");
        setAuthor("Jane Doe");
        addItem("DIRT", 0);
        setShowCount(true);
        addStringPrompt("Obj Name", "Set a name for the objective", "Break ANY block");
        setCountPrompt("Set the amount of blocks to break");
        setDisplay("%Obj Name%: %count%");
    }
    
    @EventHandler(priority = EventPriority.LOW)
    public void onBlockBreak(BlockBreakEvent event) {
        Player player = event.getPlayer();
        for (Quest q : quests.getQuester(player.getUniqueId()).getCurrentQuests().keySet()) {
            incrementObjective(player, this, 1, q);
            return;
        }
    }
}
```
{% endtab %}
{% endtabs %}

In the constructor of your class, you may use any of the following methods:

| Method | Description |
| :--- | :--- |
| setName | Sets the name of the Custom Objective. |
| setAuthor | Sets the author of the Custom Objective \(you!\). |
| addItem | Add an item which might appear in overlay plugins like QuestsGUI. |
| setShowCount | Sets whether the quest editor may set the count \(number of times player must repeat task\). Default is "true". _This will apply to all prompts added with \#addStringPrompt unless disabled._ |
| setCountPrompt | Sets the prompt description for the user to enter the count for the objective. Default is "Enter number". |
| setDisplay | Sets how the objective is displayed in /quests list and the Quest Journal. For placeholders, use `%count%` to get the value of \#setShowCount, and \#addStringPrompt titles for user input \(such as `%Item Name%` in the second example\). Default is "Progress: %count%". |
| addStringPrompt | Adds a new editor prompt with the specified title, description, and default value for your Custom Objective. Quest editors may input a string which is up to you to parse. |

Inside your EventHandlers \(if applicable\), determine whether the player has completed part or all of the objective, and then use \#incrementObjective to advance the player. The first and the second argument of \#incrementObjective should always be the player and 'this' respectively. The third argument is how much to increment the objective by, while the last is the quest for which to apply the increment to. Even if your objective does not have a count, you must still use \#incrementObjective - use an increment of 1 to signal that the objective has been completed.

The `Map<String, Object>` contains the data that the quest editor provided. In this example, the data keys are the item names, whereas the values are the user's input for your prompt \(which _can_ be null\). Also, note that while the values are of type Object, they were cast to type String internally. You must perform manual type-conversion if you want to obtain integers, booleans, et al.

