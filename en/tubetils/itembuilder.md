Title: Item-Builder

## What is the Item-Builder?

With the Item-Builder, items or item stacks can be created quickly and easily (as the name suggests).

Many different types of items or item stacks can thus be created within a few seconds, which would otherwise require very long and complicated methods.

## Create a new Item-Builder-Instance

In order to use the Item-Builder, a new instance must first be created. The instance can either be used for an entire plugin or a new instance can be created for each class. There is no difference, but it is recommended to create one instance, as the creation of further instances can consume more resources (RAM).


In the following example, we create a new instance in the main class of our example plugin. Using the `getItemBuilder` method created below, the instance can be used in any class:

```java
package de.tubeof.tubetils.usage.example.main;

import de.tubeof.tubetils.api.itembuilder.ItemBuilder;
import org.bukkit.plugin.java.JavaPlugin;

public class TubeTilsExample extends JavaPlugin {

    private static final ItemBuilder itemBuilder = new ItemBuilder("TubeTilsExampleItemBuilder");

    @Override
    public void onEnable() {
        //Your onEnable Code
    }

    @Override
    public void onDisable() {
        //Your onDisable Code
    }
    

    public static ItemBuilder getItemBuilder() {
        return itemBuilder;
    }
}
```

## Creating multiple instances

The creation of several instances is no problem, as already described in the last point. However, we recommend that one instance is created and used for the entire plugin in order to save resources.

## Creating Item-Stacks

The creation of items is very easy and quickly done after the instance has been created.
We use the `PlayerJoinEvent` for our example and add items to the player's inventory.

???+ info
    TubeTils still offers conditional support for older versions, so sub-IDs can also be used for items that were previously used.

### Simple Item-Stacks

In this example, we use the method `itemBuilder#normalItem(Material.EXAMPLE, 0, "Example Name")` to create an item of type `STONE` and assign a name:

```java
package de.tubeof.tubetils.usage.example.listener;

import de.tubeof.tubetils.api.itembuilder.ItemBuilder;
import de.tubeof.tubetils.usage.example.main.TubeTilsExample;
import org.bukkit.Material;
import org.bukkit.entity.Player;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.event.player.PlayerJoinEvent;
import org.bukkit.inventory.PlayerInventory;

public class Join implements Listener {

    private final ItemBuilder itemBuilder = TubeTilsExample.getItemBuilder();

    @EventHandler
    public void onJoin(PlayerJoinEvent event) {
        Player player = event.getPlayer();
        PlayerInventory inventory = player.getInventory();

        inventory.addItem(itemBuilder.normalItem(Material.STONE_AXE, 0, "§cMega Axe"));
    }
}
```

### Lore Item-Stacks

Items can be created with an additional text (Lore). These look like this as an example:
![](https://static.planetminecraft.com/files/resource_media/screenshot/1348/WGbtDvE_6764492.jpg)

**2 Line Lore-Item**

In this example, we create an item with 2 lines of text. There is already a method from the Item-Builder for this, as 2 lines are used most often and is therefore a quick method to create such items.

In this example we use the method `itemBuilder#twoLoreItem(Material.EXAMPLE, 0, "Example Name", "Example Lore 1", "Example Lore 2")`:

```java
package de.tubeof.tubetils.usage.example.listener;

import de.tubeof.tubetils.api.itembuilder.ItemBuilder;
import de.tubeof.tubetils.usage.example.main.TubeTilsExample;
import org.bukkit.Material;
import org.bukkit.entity.Player;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.event.player.PlayerJoinEvent;
import org.bukkit.inventory.PlayerInventory;

public class Join implements Listener {

    private final ItemBuilder itemBuilder = TubeTilsExample.getItemBuilder();

    @EventHandler
    public void onJoin(PlayerJoinEvent event) {
        Player player = event.getPlayer();
        PlayerInventory inventory = player.getInventory();

        inventory.addItem(itemBuilder.twoLoreItem(Material.STONE_SWORD, 0, "§cCool Sword", "§7This is a normal item.", "§7It was created using TubeTils"));

    }
}
```

**Multiple Line Lore-Item**

The `itemBuilder#customLoresItem(Material.EXAMPLE, 0, "Example Name", ArrayList<String> lores)` method can also be used to create items with any number of lines, as shown here in this example:

```java
package de.tubeof.tubetils.usage.example.listener;

import de.tubeof.tubetils.api.itembuilder.ItemBuilder;
import de.tubeof.tubetils.usage.example.main.TubeTilsExample;
import org.bukkit.Material;
import org.bukkit.entity.Player;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.event.player.PlayerJoinEvent;
import org.bukkit.inventory.PlayerInventory;

import java.util.ArrayList;

public class Join implements Listener {

    private final ItemBuilder itemBuilder = TubeTilsExample.getItemBuilder();

    @EventHandler
    public void onJoin(PlayerJoinEvent event) {
        Player player = event.getPlayer();
        PlayerInventory inventory = player.getInventory();

        ArrayList<String> lores = new ArrayList<>();
        lores.add("Lore 1");
        lores.add("Lore 2");
        lores.add("WHOHW! XY Line!");

        inventory.addItem(itemBuilder.customLoresItem(Material.STONE_SWORD, 0, "§cMultiple Line Lore-Item", lores));

    }
}
```

**2 Line Lore-Skull-Item**

Player-Skulls can also be created in the form of an item with a lore. Here again there is a method with which two lines can be defined, as these are used most often. In this example, we now create a skull item with a lore using the method `itemBuilder#loreSkullItem("Player123", "Example Name", "Example Lore 1", "Example Lore 2")`:

```java
package de.tubeof.tubetils.usage.example.listener;

import de.tubeof.tubetils.api.itembuilder.ItemBuilder;
import de.tubeof.tubetils.usage.example.main.TubeTilsExample;
import org.bukkit.entity.Player;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.event.player.PlayerJoinEvent;
import org.bukkit.inventory.PlayerInventory;

public class Join implements Listener {

    private final ItemBuilder itemBuilder = TubeTilsExample.getItemBuilder();

    @EventHandler
    public void onJoin(PlayerJoinEvent event) {
        Player player = event.getPlayer();
        PlayerInventory inventory = player.getInventory();

        inventory.addItem(itemBuilder.loreSkullItem("ExamplePlayer123", "Player Skull Item", "Lore 1", "Lore 2"));

    }
}
```
