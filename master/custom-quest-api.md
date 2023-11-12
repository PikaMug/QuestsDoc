# Quêtes customisées API

{% hint style="info" %}
ALERTE: Ces informations sont destinées aux développeurs. Apprenez d'abord à utiliser Java !
{% endhint %}

### Ajouter à votre projet

Si vous utilisez Maven ou un autre outil de gestion de projet, ajoutez la dernière version de Quests via le service CodeMC.

```xml
<repository>
  <id>codemc-repo</id>
  <url>https://repo.codemc.io/repository/maven-public/</url>
</repository>
```

A menos que diseñe un proyecto multiplataforma, querrá definir el artefacto principal.

```xml
<dependency>
  <groupId>me.blackvein.quests</groupId>
  <artifactId>quests-core</artifactId>
  <version>VERSION</version>
</dependency>
```

### Apprendre l'interface

Quests fournit une API simple pour créer des exigences, des récompenses et des objectifs personnalisés. Pour commencer, assurez-vous que vous compilez avec la version 4.0.0 ou supérieure. Une fois que vous avez fini de suivre ce guide, utilisez le dossier /Quests/modules comme destination pour votre fichier jar fini et compilé. Si vous distribuez votre module, assurez-vous d'informer l'utilisateur de l'emplacement final et correct du dossier.

#### API des exigences

Construire une exigence de quêtes est très simple. Pour commencer, créez une classe Java qui étend la classe CustomRequirement. Après cela, consultez cet exemple d'exigence personnalisée où le joueur doit avoir un nom particulier pour entreprendre la quête :

```java
package xyz.janedoe;

import java.util.Map;
import org.bukkit.entity.Player;
import me.blackvein.quests.CustomRequirement;

public class NameRequirement extends CustomRequirement {
    // Construire l'exigence
    public NameRequirement() {
        this.setName("Exigence de nom");
        this.setAuthor("Jane Doe");
        this.addItem("NAME_TAG", 0);
        this.addStringPrompt("Name", "Entrez la valeur que le nom du joueur doit contenir afin de prendre la quête", null);
        this.addStringPrompt("Case-Sensitive", "La vérification doit-elle être sensible à la casse ou non ? (Entrer \'true\' ou \'false\'", null);
	this.setDisplay("Désolé, vous n'êtes pas sur la liste.");
    }
    
    // Tester si un joueur a satisfait à l'exigence
    @Override
    public boolean testRequirement(Player player, Map<String, Object> data) {
	String caseSensitive = (String) data.get("Case-Sensitive");
		
	// Vérifiez si le nom doit être sensible à la casse
	if (caseSensitive.equalsIgnoreCase("true")) {
	    // Marquer l'exigence comme satisfaite si le nom correspond
	    return player.getName().contains((String)data.get("Name"));
	} else {
	    // Marquer l'exigence comme satisfaite si le nom correspond, en ignorant la casse
	    return player.getName().toLowerCase().contains(((String)data.get("Name")).toLowerCase());
	}
    }
}
```

Dans le constructeur de votre classe, vous pouvez utiliser l'une des méthodes suivantes :

| Méthode           | Description                                                                                                                                                                                                     |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| setName()         | Définit le nom de l'objectif personnalisé.                                                                                                                                                                      |
| setAuthor()       | Définit l'auteur de l'objectif personnalisé (vous !).                                                                                                                                                           |
| addItem()         | Ajoutez un élément qui pourrait apparaître dans les plugins de superposition comme QuestsGUI.                                                                                                                   |
| setDisplay        | Définit le mode d'affichage de l'exigence en cas d'échec.                                                                                                                                                       |
| addStringPrompt() | Ajoute une nouvelle invite d'éditeur avec le titre, la description et la valeur par défaut spécifiés pour votre objectif personnalisé. Les éditeurs de quête peuvent saisir une chaîne que vous devez analyser. |

À l'intérieur de #testRequirement, vous exécutez votre logique pour déterminer si le joueur satisfait à l'exigence, renvoyant true s'il le fait et false s'il ne le fait pas.

La carte de données contient les données que la personne qui a créé la quête lui a données. Dans cet exemple, la carte de données contient les deux valeurs pour 'Name' et 'Case-Sensitive'. Notez également que même si les valeurs sont de type Object, elles ont été converties en type String en interne. Vous devez effectuer une conversion de type manuelle si vous souhaitez obtenir des entiers, des booléens, etc.

#### API de récompense

Construire une récompense de quêtes est très simple. Pour commencer, créez une classe Java qui étend la classe CustomReward. Après cela, consultez cet exemple de récompense personnalisée où un joueur obtient un inventaire GUI contenant du fer, de l'or et des diamants :

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
    // Construire la récompense
    public LootReward() {
        this.setName("Butin de récompense");
        this.setAuthor("Jane Doe");
        this.addItem("CHEST", 0);
        this.setRewardName("Coffre de butin: %Title%");
        this.addStringPrompt("Title", "Titre de l'interface d'inventaire de butin.", null);
        this.addStringPrompt("NumIron", "Entrez le nombre de lingots de fer à donner dans le coffre à butin.", null);
        this.addStringPrompt("NumGold", "Entrez le nombre de lingots d'or à donner dans le coffre à butin.", null);
        this.addStringPrompt("NumDiamond", "Entrez le nombre de diamants à donner dans le coffre à butin.", null);
    }
    
    // Donner une récompense de butin à un joueur
    @Override
    public void giveReward(Player player, Map<String, Object> data) {
        String title = (String) data.get("Title");
        int numIron = 0;
        int numGold = 0;
        int numDiamond = 0;
        
        // Tentative de chargement de l'entrée utilisateur sous forme d'entiers
        try {
            numIron = Integer.parseInt((String) data.get("NumIron"));
        } catch (NumberFormatException nfe) {
        	Bukkit.getLogger().severe("La récompense de butin a un numéro de fer invalide: " + numIron);
        }
        try {
            numGold = Integer.parseInt((String) data.get("NumGold"));
        } catch (NumberFormatException nfe) {
        	Bukkit.getLogger().severe("La récompense de butin a un numéro d'or invalide: " + numGold);
        }
        try {
            numDiamond = Integer.parseInt((String) data.get("NumDiamond"));
        } catch (NumberFormatException nfe) {
        	Bukkit.getLogger().severe("La récompense de butin a un numéro de diamands invalide: " + numDiamond);
        }
        
        // Créer un inventaire temporaire pour y ajouter des objets
        Inventory inv = Bukkit.getServer().createInventory(player, 3, title);
        int slot = 0;

        // Vérifier si le montant est supérieur à la valeur par défaut
        if (numIron > 0) {
            // Ajoutez un objet à l'emplacement actuel dans l'inventaire temporaire, puis préparez l'emplacement suivant
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
        
        // Ouvrir l'inventaire temporaire pour que le joueur accepte les objets
        player.openInventory(inv);
    }
}
```

Dans le constructeur de votre classe, vous pouvez utiliser l'une des méthodes suivantes :

| Méthode         | Description                                                                                                                                                                                                     |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| setName         | Définit le nom de l'objectif personnalisé.                                                                                                                                                                      |
| setAuthor       | Définit l'auteur de l'objectif personnalisé (vous !).                                                                                                                                                           |
| addItem         | Ajoutez un élément qui pourrait apparaître dans les plugins de superposition comme QuestsGUI.                                                                                                                   |
| setRewardName   | Définit le nom de la récompense (texte qui apparaîtra lorsque le joueur termine la quête) de la récompense personnalisée.                                                                                       |
| addStringPrompt | Ajoute une nouvelle invite d'éditeur avec le titre, la description et la valeur par défaut spécifiés pour votre objectif personnalisé. Les éditeurs de quête peuvent saisir une chaîne que vous devez analyser. |

À l'intérieur de #giveReward est l'endroit où vous exécutez votre logique pour donner au joueur tout ce que votre récompense personnalisée donne. La carte de données contient les données que la personne qui a créé la quête lui a données. Dans cet exemple, la carte de données contient quatre valeurs : une pour le titre de l'interface graphique et trois pour la quantité de fer/or/diamants. Notez également que même si les valeurs sont de type Object, elles ont été converties en type String en interne. Vous devez effectuer une conversion de type manuelle si vous souhaitez obtenir des entiers, des booléens, etc.

#### API des objectifs

Construire un objectif de quête est un peu plus compliqué que les exigences ou les récompenses. Pour commencer, créez une classe Java qui étend la classe CustomObjective. Si vous souhaitez capturer l'un des événements de Bukkit, vous devrez implémenter la classe d'écoute (Les quêtes se chargeront de l'enregistrer pour vous). Après cela, consultez ces exemples d'objectif personnalisé :

{% tabs %}
{% tab title="Exemple 1" %}
```java
// Le joueur doit acquérir une certaine expérience pour avancer

package xyz.janedoe;

import me.blackvein.quests.CustomObjective;
import me.blackvein.quests.Quest;
import me.blackvein.quests.Quests;

import org.bukkit.Bukkit;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.event.player.PlayerExpChangeEvent;

public class ExperienceObjective extends CustomObjective implements Listener {
    // Obtenir le plugin Quêtes
    Quests qp = (Quests)Bukkit.getServer().getPluginManager().getPlugin("Quests");
	
    // Construire l'objectif
    public ExperienceObjective() {
        this.setName("Objectif d'expérience");
        this.setAuthor("Jane Doe");
        this.addItem("BOOK", 0);
        this.setShowCount(true);
        this.setCountPrompt("Saisissez les points d'expérience que le joueur doit acquérir:");
        this.setDisplay("Acquérir des points d'expérience : %count%");
    }

    // Attrapez l'événement Bukkit pour un joueur gagnant / perdant de l'expérience
    @EventHandler
    public void onPlayerExpChange(PlayerExpChangeEvent evt) {
       // Assurez-vous d'évaluer toutes les quêtes actuelles du joueur
        for (Quest quest : qp.getQuester(evt.getPlayer().getUniqueId()).getCurrentQuests().keySet()) {
            // Vérifie si le joueur a gagné plus d'expérience qu'il n'en a perdu
            if (evt.getAmount() > 0) {
                // Ajoutez à la progression de l'objectif, en le complétant si les exigences ont été remplies
                incrementObjective(evt.getPlayer(), this, evt.getAmount(), quest);
            }
        }
    }
}
```
{% endtab %}

{% tab title="Exemple 2" %}
```java
// Exiger que le joueur laisse tomber un certain nombre d'un certain type d'objet.

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
    // obtenir le plugin Quêtes
    Quests qp = (Quests)Bukkit.getServer().getPluginManager().getPlugin("Quests");

    // Construire l'objectif
    public DropItemObjective() {
        this.setName("Objectif de l'objet à jeter");
        this.setAuthor("Jane Doe");
        this.addItem("ANVIL", 0); // Quests 4.0.0+ uniquement
        this.setShowCount(true);
        this.setCountPrompt("Entrez le montant que le joueur doit déposer:");
        this.setDisplay("Jeter %Item Name%: %count%");
        this.addStringPrompt("Item Name", "Entrez le nom de l'objet que le joueur doit déposer", "DIRT");
    }

    // Attrapez l'événement Bukkit pour un joueur laissant tomber un objet
    @EventHandler
    public void onPlayerDropItem(PlayerDropItemEvent evt){
    	// Assurez-vous d'évaluer toutes les quêtes actuelles du joueur
    	for (Quest quest : qp.getQuester(evt.getPlayer().getUniqueId()).getCurrentQuests().keySet()) {
    	    Map<String, Object> map = getDataForPlayer(evt.getPlayer(), this, quest);
	    if (map == null) {
	        continue;
            }
            ItemStack stack = evt.getItemDrop().getItemStack();
            String userInput = (String) map.get("Item Name");
            EntityType type = EntityType.fromName(userInput);
            // Erreur d'affichage si le nom d'élément spécifié par l'utilisateur n'est pas valide
            if (type == null) {
            	Bukkit.getLogger().severe("L'objectif d'élément àjeter a un nom d'élément non valide: " + userInput);
            	continue;
            }
            // Vérifiez si l'élément que le joueur a déposé est celui spécifié par l'utilisateur
            if (evt.getItemDrop().getItemStack().getType().equals(type)) {
    		// Ajouter à la progression de l'objectif, en le complétant si les exigences ont été remplies
            	incrementObjective(evt.getPlayer(), this, stack.getAmount(), quest);
            }
    	}
    }
}
```
{% endtab %}

{% tab title="Exemple 3" %}
```java
// Autoriser le joueur à casser N'IMPORTE QUEL bloc plutôt qu'un spécifique

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
   // Récupérer le plugin Quêtes
    private static Quests quests = (Quests) Bukkit.getServer().getPluginManager().getPlugin("Quests");
    
    public AnyBreakBlockObjective() {
        setName("Objectif casser des blocs");
        setAuthor("Jane Doe");
        addItem("DIRT", 0);
        setShowCount(true);
        addStringPrompt("Obj Name", "Définir un nom pour l'objectif", "Casser tous les bocs");
        setCountPrompt("Définir le nombre de blocs à casser");
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

Dans le constructeur de votre classe, vous pouvez utiliser l'une des méthodes suivantes :

| Méthode         | Description                                                                                                                                                                                                                                                                                                                                     |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| setName         | Définit le nom de l'objectif personnalisé.                                                                                                                                                                                                                                                                                                      |
| setAuthor       | Sets l'auteur de l'objectif personnalisé (vous !).                                                                                                                                                                                                                                                                                              |
| addItem         | Ajoutez un élément qui pourrait apparaître dans les plugins de superposition comme QuestsGUI.                                                                                                                                                                                                                                                   |
| setShowCount    | Définit si l'éditeur de quête peut définir le décompte (nombre de fois où le joueur doit répéter la tâche). La valeur par défaut est "vrai". _Cela s'appliquera à toutes les invites ajoutées avec #addStringPrompt, sauf si elles sont désactivées._                                                                                           |
| setCountPrompt  | Définit la description de l'invite permettant à l'utilisateur d'entrer le nombre pour l'objectif. La valeur par défaut est "Entrer le numéro".                                                                                                                                                                                                  |
| setDisplay      | Définit la façon dont l'objectif est affiché dans la liste /quests et le journal des quêtes. Pour les espaces réservés, utilisez `%count%` pour obtenir la valeur de #setShowCount et les titres #addStringPrompt pour l'entrée utilisateur (comme `%Item Name%` dans le deuxième exemple). La valeur par défaut est « Progression : %count% ». |
| addStringPrompt | Ajoute une nouvelle invite d'éditeur avec le titre, la description et la valeur par défaut spécifiés pour votre objectif personnalisé. Les éditeurs de quête peuvent saisir une chaîne que vous devez analyser.                                                                                                                                 |

À l'intérieur de vos EventHandlers (le cas échéant), déterminez si le joueur a atteint tout ou partie de l'objectif, puis utilisez #incrementObjective pour faire avancer le joueur. Le premier et le deuxième argument de #incrementObjective doivent toujours être respectivement le joueur et 'this'. Le troisième argument est de combien incrémenter l'objectif, tandis que le dernier est la quête à laquelle appliquer l'incrément. Même si votre objectif n'a pas de décompte, vous devez toujours utiliser #incrementObjective - utilisez un incrément de 1 pour signaler que l'objectif a été atteint.

Le `Map<String, Object>` contient les données fournies par l'éditeur de quête. Dans cet exemple, les clés de données sont les noms des éléments, tandis que les valeurs sont l'entrée de l'utilisateur pour votre invite (qui _peut_ être null). Notez également que même si les valeurs sont de type objets, elles ont été converties en type String en interne. Vous devez effectuer une conversion de type manuelle si vous souhaitez obtenir des entiers, des booléens, etc.
