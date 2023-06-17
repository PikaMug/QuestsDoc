# Custom Quest API

{% hint style="info" %}
**Тревога:** Тази информация е предназначена за разработчици. Научете първо как да използвате Java!
{% endhint %}

### Add to your project


Ако използвате Maven или друг инструмент за управление на проекти, добавете най-новата версия на Quests чрез услугата CodeMC.

```xml
<repository>
  <id>codemc-repo</id>
  <url>https://repo.codemc.io/repository/maven-public/</url>
</repository>
```
```xml
<dependency>
  <groupId>me.blackvein.quests</groupId>
  <artifactId>quests-api</artifactId>
  <version>VERSION</version>
</dependency>
```

You may also need the core module.

```xml
<dependency>
  <groupId>me.blackvein.quests</groupId>
  <artifactId>quests-core</artifactId>
  <version>VERSION</version>
</dependency>
```

### Научете интерфейса

Quests предоставя прост API за създаване на персонализирани изисквания, награди и цели. Като начало се уверете, че компилирате спрямо версия 4.0.0 или по-нова. След като приключите с това ръководство, използвайте папката _/Quests/modules_ като дестинация за вашия завършен и компилиран jar. Ако разпространявате вашия модул, не забравяйте да информирате крайния потребител за правилното местоположение на папката.

#### Requirements API

Изграждането на изискване на задача е много просто. За да започнете, създайте Java клас, който разширява класа като CustomRequirement. След това вижте този пример за персонализирано изискване, при което играчът трябва да има конкретно име, за да вземе задачата:

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

В конструктора на вашия клас можете да използвате някой от следните методи:

| Методи | Описание |
| :--- | :--- |
| setName | Задава името на персонализираната цел. |
| setAuthor | Задава автора на персонализираната цел \(ти!\). |
| addItem | Добавете предмет, който може да се появи в плъгин за наслагване като QuestsGUI. |
| setDisplay | Задава как изискването да се показва при неуспех. |
| addStringPrompt | Добавя нова подкана за радактор с указано заглавие, описание и стойност по подразбиране за вашата персонализирана цел. Редактора на задачи може да въведе низ, който зависи от вас да анализирате |

Вътре в \#testRequirement е мястото където изпълнявате вашата логика, за да определите дали играчът преминава изискването, връщайки 'true', ако го направи, и 'false' ако не го направи. 

Картата с данни съдържа данните, които лицето, създало задачата, й е дало. В този пример картата на данните съдържа двете стойности за „Име“ и „Отчитане на малки и големи букви“. Също така имайте предвид, че въпреки че стойностите са от тип Object, те са преобразувани вътрешно към тип String. Трябва да извършите ръчно преобразуване на типа, ако искате да получите integers, booleans стойности и др.

#### Rewards API

Изграждането на награда за задачи е много просто. За да започнете, създайте Java клас, който разширява класа CustomReward. След това вижте този пример за персонализирана награда, при която играчът получава GUI инвентар, който се появява, съдържащ желязо, злато и диаманти:

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

В конструктора на вашия клас можете да използвате някой от следните методи

| Методи | Описание |
| :--- | :--- |
| setName | Задава името на персонализираната цел. |
| setAuthor | Задава автора на персонализираната цел \(ти!\). |
| addItem | Добавете предмет, който може да се появи в плъгин за наслагване като QuestsGUI. |
| setDisplay | Задава как изискването да се показва при неуспех. |
| addStringPrompt | Добавя нова подкана за радактор с указано заглавие, описание и стойност по подразбиране за вашата персонализирана цел. Редактора на задачи може да въведе низ, който зависи от вас да анализирате |

Вътре в \#giveReward е мястото където изпълнявате вашата логика, за да определите дали играчът преминава изискването, връщайки 'true', ако го направи, и 'false' ако не го направи.

#### Objectives API

Изграждането на цел за задача е малко по-сложно от изискванията или наградите. За да започнете, създайте Java клас, който разширява класа CustomObjective. Ако искате да хванете някой Event от Bukkit, ще трябва да внедрите класа Listener \(Quests ще се погрижи за регистрацията на събитието вместо вас\). След това вижте тези примери за персонализираната цел:

{% tabs %}
{% tab title="Пример 1" %}
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

{% tab title="Пример 2" %}
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

{% tab title="Пример 3" %}
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

В конструктора на вашия клас можете да използвате някой от следните методи:

| Методи | Описание |
| :--- | :--- |
| setName | Задава името на персонализираната цел. |
| setAuthor | Задава автора на персонализираната цел \(ти!\). |
| addItem | Добавете предмет, който може да се появи в плъгин за наслагване като QuestsGUI. |
| setShowCount | Определя дали редакторът на задачи може да задавя броя \(брой пъти, когато играчът трябва да повтори целта\). По подразбиране е "true". _Това ще се прилага за всички подкани, дабавени с \#addStringPrompt, освен ако не е забранено._ |
| setCountPrompt | Задава подканящото описание за потребителя да въведе броя за целта. По подразбиране е "Въведете номер". |
| setDisplay | Задава начина, по който целта се показва в "/quests list" и дневника на задачите. За контейнерите използвайте %count%, за да получите стойността на \#setShowCount, и \#addStringPrompt заглавия за въвеждане от потребителя \(като "Item Name" във втория пример\). По подразбиране е "Progress: %count%". |
| addStringPrompt | Добавя нова подкана за радактор с указано заглавие, описание и стойност по подразбиране за вашата персонализирана цел. Редактора на задачи може да въведе низ, който зависи от вас да анализирате |


Във вашият EventHandlers \(ако е приложимо\), определете дали играчът е изпълнил част или цялата цел и след това използвайте \#incrementObjective, за да напреднете играча. Първият и вторият аргумент на \#incrementObjective винаги трябва да бъдат съответно играчът и 'this'. Третият аргумент е с колко да се увеличи целта, докато последният е търсенете, към което да се приложи увеличението. Дори ако вашата цел няма брой, пак трябва да използвате \#incrementObjective - използвайте увеличение от 1, за да сигнализирате, че целта е изпълнена.

`Map<String, Object>` съдържа данните, предоставени от редактора на задачи. В този пример ключовете за данни са имената на елементите, докато стойностите са въведените от потребителя за вашата подкана \(която _може_ да бъде _null_\). Също така имайте предвид, че въпреки, че стойностите са от тип Object, те са преобразувани вътрешно към тип String. Трябва да извършите ръчно преобразуване на типа, ако искате да получите цели integers, booleans стойности и др.

 