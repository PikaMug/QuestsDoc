# 自定义任务 API

{% hint style="info" %}
**注意：** 此信息面向开发者。请先学习 Java 基础知识！
{% endhint %}

### 添加到您的项目

为了快速入门，GitHub 上提供了一个模块模板项目：[这里](https://github.com/PikaMug/ExampleQuestsModule)。

如果您使用 Maven 或其他项目管理工具，请通过 CodeMC 服务添加最新版本的 Quests。

```xml
<repository>
  <id>codemc-repo</id>
  <url>https://repo.codemc.io/repository/maven-public/</url>
</repository>
```

除非设计跨平台项目，否则您需要定义核心 artifact。

```xml
<dependency>
  <groupId>me.pikamug.quests</groupId>
  <artifactId>quests-core</artifactId>
  <version>VERSION</version>
</dependency>
```

### 了解接口

Quests 提供了一个简单的 API，用于创建自定义要求、奖励和目标。首先，确保您针对 4.0.0 或更高版本进行编译。完成本指南后，将编译完成的 jar 文件放入 *Quests/modules* 文件夹。如果要分发您的模块，请务必告知最终用户正确的文件夹位置。

以下示例假设您正在为基于 Bukkit 的软件创建项目。

#### 要求 API

创建 Quests 自定义要求非常简单。首先，创建一个继承 BukkitCustomRequirement 类的 Java 类。然后，查看以下示例：玩家必须拥有特定名称才能接受任务。

```java
package xyz.janedoe;

import java.util.Map;
import org.bukkit.entity.Player;
import me.pikamug.quests.module.BukkitCustomRequirement;

public class NameRequirement extends BukkitCustomRequirement {
    // 构造要求
    public NameRequirement() {
        setName("名称要求");
        setAuthor("Jane Doe");
        setItem("NAME_TAG", (short)0);
        addStringPrompt("Name", "输入玩家名称必须包含的值才能接受任务", null);
        addStringPrompt("Case-Sensitive", "检查是否区分大小写？（输入 'true' 或 'false'）", null);
        setDisplay("抱歉，您不在名单上。");
    }
    
    // 测试玩家是否满足要求
    @Override
    public boolean testRequirement(Player player, Map<String, Object> data) {
	      String caseSensitive = (String) data.get("Case-Sensitive");
		
	      // 检查是否需要区分大小写
	      if (caseSensitive.equalsIgnoreCase("true")) {
	          // 如果名称匹配，则标记要求已满足
	          return player.getName().contains((String)data.get("Name"));
	      } else {
	          // 如果名称匹配（忽略大小写），则标记要求已满足
	          return player.getName().toLowerCase().contains(((String)data.get("Name")).toLowerCase());
	      }
    }
}
```

在类的构造函数中，您可以使用以下任意方法：

| 方法              | 描述                                                                                     |
| ----------------- | ---------------------------------------------------------------------------------------- |
| setName           | 设置自定义要求的名称。                                                                   |
| setAuthor         | 设置自定义要求的作者（您自己！）。                                                       |
| setItem           | 设置一个可能在如 QuestsGUI 等覆盖插件中显示的物品。                                       |
| setDisplay        | 设置要求失败时显示的文本。                                                               |
| addStringPrompt   | 为自定义要求添加一个新的编辑器提示，包括指定标题、描述和默认值。任务编辑者可以输入字符串，由您自行解析。 |

在 #testRequirement 方法中执行逻辑，判断玩家是否通过要求：通过返回 true，未通过返回 false。

data Map 包含任务创建者提供的数据。本示例中，data Map 包含 'Name' 和 'Case-Sensitive' 两个值。请注意，虽然值类型为 Object，但内部已强制转换为 String。如果需要获取整数、布尔值等，必须手动进行类型转换。

#### 奖励 API

创建 Quests 自定义奖励非常简单。首先，创建一个继承 BukkitCustomReward 类的 Java 类。然后，查看以下示例：玩家完成任务后弹出包含铁锭、金锭和钻石的 GUI 背包。

```java
package xyz.janedoe;

import java.util.Map;

import org.bukkit.Bukkit;
import org.bukkit.Material;
import org.bukkit.entity.Player;
import org.bukkit.inventory.Inventory;
import org.bukkit.inventory.ItemStack;

import me.pikamug.quests.module.BukkitCustomReward;

import java.util.UUID;

public class LootReward extends BukkitCustomReward {
    // 构造奖励
    public LootReward() {
        setName("战利品奖励");
        setAuthor("Jane Doe");
        setItem("CHEST", (short)0);
        setDisplay("战利品箱：%Title%");
        addStringPrompt("Title", "输入战利品背包界面的标题。", null);
        addStringPrompt("NumIron", "输入要给予的铁锭数量。", null);
        addStringPrompt("NumGold", "输入要给予的金锭数量。", null);
        addStringPrompt("NumDiamond", "输入要给予的钻石数量。", null);
    }
    
    // 给予玩家战利品奖励
    @Override
    public void giveReward(UUID uuid, Map<String, Object> data) {
        final Player player = Bukkit.getPlayer(uuid);
        if (player == null) {
            Bukkit.getLogger().severe("Player was null for UUID " + uuid);
            return;
        }
        String title = (String) data.get("Title");
        int numIron = 0;
        int numGold = 0;
        int numDiamond = 0;
        
        // 尝试将用户输入加载为整数
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
        
        // 创建临时背包以添加物品
        Inventory inv = Bukkit.getServer().createInventory(player, 3, title);
        int slot = 0;

        // 检查数量是否大于默认值
        if (numIron > 0) {
            // 将物品添加到临时背包的当前槽位，然后准备下一个槽位
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
        
        // 为玩家打开临时背包以接受物品
        player.openInventory(inv);
    }
}
```

在类的构造函数中，您可以使用以下任意方法：

| 方法              | 描述                                                                                     |
| ----------------- | ---------------------------------------------------------------------------------------- |
| setName           | 设置自定义奖励的名称。                                                                   |
| setAuthor         | 设置自定义奖励的作者（您自己！）。                                                       |
| setItem           | 设置一个可能在如 QuestsGUI 等覆盖插件中显示的物品。                                       |
| setDisplay        | 设置奖励名称（玩家完成任务时显示的文本）。                                               |
| addStringPrompt   | 为自定义奖励添加一个新的编辑器提示，包括指定标题、描述和默认值。任务编辑者可以输入字符串，由您自行解析。 |

在 #giveReward 方法中执行逻辑，向玩家发放自定义奖励。data Map 包含任务创建者提供的数据。本示例中，data Map 包含四个值：GUI 标题一个，以及铁/金/钻石数量三个。请注意，虽然值类型为 Object，但内部已强制转换为 String。如果需要获取整数、布尔值等，必须手动进行类型转换。

#### 目标 API

创建 Quests 自定义目标比要求或奖励稍复杂一些。首先，创建一个继承 BukkitCustomObjective 类的 Java 类。如果需要捕获 Bukkit 的某个事件，则需实现 Listener 接口（Quests 会为您自动注册）。然后，查看以下自定义目标示例：

{% tabs %}
{% tab title="示例 1" %}

```java
// 玩家必须获得一定数量的经验才能推进

package xyz.janedoe;

import me.pikamug.quests.module.BukkitCustomObjective;
import me.pikamug.quests.Quest;
import me.pikamug.quests.Quests;

import org.bukkit.Bukkit;
import org.bukkit.event.EventHandler;
import org.bukkit.event.player.PlayerExpChangeEvent;

public class ExperienceObjective extends BukkitCustomObjective {
    // 获取 Quests 插件
    Quests qp = (Quests) Bukkit.getServer().getPluginManager().getPlugin("Quests");
	
    // 构造目标
    public ExperienceObjective() {
        setName("经验目标");
        setAuthor("Jane Doe");
        setItem("BOOK", (short)0);
        setShowCount(true);
        setCountPrompt("输入玩家必须获取的经验值数量：");
        setDisplay("获取经验值：%count%");
    }

    // 捕获玩家获得/丢失经验的 Bukkit 事件
    @EventHandler
    public void onPlayerExpChange(PlayerExpChangeEvent evt) {
        Quester quester = qp.getQuester(evt.getPlayer().getUniqueId());
        // 确保为玩家所有当前任务进行评估
        for (Quest quest : quester.getCurrentQuests().keySet()) {
            // 检查玩家是否获得经验，而不是丢失
            if (evt.getAmount() > 0) {
                // 增加目标进度，如果满足要求则完成
                incrementObjective(quester.getUUID(), this, quest, evt.getAmount());
                // 可选：与队伍成员共享进度（如果适用）
                quester.dispatchMultiplayerEverything(quest, ObjectiveType.CUSTOM,
                        (final Quester q, final Quest cq) -> {
                           incrementObjective(q.getUUID(), this, quest, evt.getAmount());
                           return null;
                });
            }
        }
    }
}
```

{% endtab %}

{% tab title="示例 2" %}

```java
// 要求玩家丢弃一定数量的特定类型物品

package xyz.janedoe;

import me.pikamug.quests.module.BukkitCustomObjective;
import me.pikamug.quests.Quest;
import me.pikamug.quests.Quests;

import org.bukkit.Bukkit;
import org.bukkit.entity.EntityType;
import org.bukkit.event.EventHandler;
import org.bukkit.event.player.PlayerDropItemEvent;
import org.bukkit.inventory.ItemStack;

public class DropItemObjective extends BukkitCustomObjective {
    // 获取 Quests 插件
    Quests qp = (Quests) Bukkit.getServer().getPluginManager().getPlugin("Quests");

    // 构造目标
    public DropItemObjective() {
        setName("丢弃物品目标");
        setAuthor("Jane Doe");
        setItem("ANVIL", (short)0);
        setShowCount(true);
        setCountPrompt("输入玩家必须丢弃的数量：");
        setDisplay("丢弃 %Item Name%：%count%");
        addStringPrompt("Item Name", "输入玩家必须丢弃的物品名称", "DIRT");
    }

    // 捕获玩家丢弃物品的 Bukkit 事件
    @EventHandler
    public void onPlayerDropItem(PlayerDropItemEvent evt){
    	// 确保为玩家所有当前任务进行评估
    	for (Quest quest : qp.getQuester(evt.getPlayer().getUniqueId()).getCurrentQuests().keySet()) {
    	    Map<String, Object> map = getDataForPlayer(evt.getPlayer(), this, quest);
	    if (map == null) {
	        continue;
            }
            ItemStack stack = evt.getItemDrop().getItemStack();
            String userInput = (String) map.get("Item Name");
            EntityType type = EntityType.fromName(userInput);
            // 如果用户指定的物品名称无效，则显示错误
            if (type == null) {
            	Bukkit.getLogger().severe("Drop Item Objective has invalid item name: " + userInput);
            	continue;
            }
            // 检查玩家丢弃的物品是否为用户指定的物品
            if (evt.getItemDrop().getItemStack().getType().equals(type)) {
    		// 增加目标进度，如果满足要求则完成
            	incrementObjective(evt.getPlayer().getUniqueId(), this, quest, stack.getAmount());
            }
    	}
    }
}
```

{% endtab %}

{% tab title="示例 3" %}

```java
// 允许玩家破坏任意方块，而不是特定方块

package xyz.janedoe;

import me.pikamug.quests.module.BukkitCustomObjective;
import me.pikamug.quests.Quest;
import me.pikamug.quests.Quests;

import org.bukkit.Bukkit;
import org.bukkit.entity.Player;
import org.bukkit.event.EventHandler;
import org.bukkit.event.EventPriority;
import org.bukkit.event.block.BlockBreakEvent;

public class AnyBreakBlockObjective extends BukkitCustomObjective {
    // 获取 Quests 插件
    private static Quests quests = (Quests) Bukkit.getServer().getPluginManager().getPlugin("Quests");
    
    public AnyBreakBlockObjective() {
        setName("破坏方块目标");
        setAuthor("Jane Doe");
        setItem("DIRT", (short)0);
        setShowCount(true);
        addStringPrompt("Obj Name", "为目标设置名称", "破坏任意方块");
        setCountPrompt("设置要破坏的方块数量");
        setDisplay("%Obj Name%：%count%");
    }
    
    @EventHandler(priority = EventPriority.LOW)
    public void onBlockBreak(BlockBreakEvent event) {
        Player player = event.getPlayer();
        for (Quest q : quests.getQuester(player.getUniqueId()).getCurrentQuests().keySet()) {
            incrementObjective(player.getUniqueId(), this, q, 1);
            return;
        }
    }
}
```

{% endtab %}
{% endtabs %}

在类的构造函数中，您可以使用以下任意方法：

| 方法              | 描述                                                                                                                                                                                                                                                             |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| setName           | 设置自定义目标的名称。                                                                                                                                                                                                                                          |
| setAuthor         | 设置自定义目标的作者（您自己！）。                                                                                                                                                                                                                             |
| setItem           | 设置一个可能在如 QuestsGUI 等覆盖插件中显示的物品。                                                                                                                                                                                                             |
| setShowCount      | 设置是否允许任务编辑者设置计数（玩家必须重复任务的次数）。默认为 "true"。*这将适用于使用 #addStringPrompt 添加的所有提示，除非禁用。*                                                                                                                             |
| setCountPrompt    | 设置用户输入目标计数的提示描述。默认为 "Enter number"。                                                                                                                                                                                                         |
| setDisplay        | 设置目标在 /quests list 和任务日志中的显示方式。占位符：使用 `%count%` 获取 #setShowCount 的值，使用 #addStringPrompt 的标题获取用户输入（如第二个示例中的 `%Item Name%`）。默认为 "Progress: %count%"。                                                               |
| addStringPrompt   | 为自定义目标添加一个新的编辑器提示，包括指定标题、描述和默认值。任务编辑者可以输入字符串，由您自行解析。                                                                                                                                                      |

在事件处理器（如果适用）中，判断玩家是否部分或全部完成目标，然后使用 #incrementObjective 推进玩家进度。#incrementObjective 的第一个和第二个参数始终应为玩家和 'this'。第三个参数为增量值，第四个参数为应用增量的任务。即使目标没有计数，也必须使用 #incrementObjective —— 使用增量 1 表示目标已完成。

`Map<String, Object>` 包含任务编辑者提供的数据。本示例中，键为物品名称，值为用户对提示的输入（可能为 null）。请注意，虽然值类型为 Object，但内部已强制转换为 String。如果需要获取整数、布尔值等，必须手动进行类型转换。