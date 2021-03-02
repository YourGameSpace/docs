Title: Cache-Container

## What is a Cache-Container?

In a Cache-Container, all kinds of values of the data types available in Java can be stored temporarily in order to be able to retrieve them at a later time.


This is very useful for Config-Files, among other things, so that IO-Resources can be saved and stored values from your Config-File can be retrieved quickly (much faster than getting data directly from the hard disk) and easily from the Cache-Container.

## Create a new Cache-Container-Instance

In order to use Cache-Containers, a new instance must be created. In the best case, this should be created from your main class. However, instances can also be created in other classes.


In our example, we create a new instance in the main class and store it in a variable so that it can later be used from all classes:

```java
package de.tubeof.tubetils.usage.example.main;

import de.tubeof.tubetils.api.cache.CacheContainer;
import org.bukkit.plugin.java.JavaPlugin;

public class TubeTilsExample extends JavaPlugin {

    private static CacheContainer cacheContainer = new CacheContainer("TubeTilsExample");

    @Override
    public void onEnable() {
        //Your onEnable Code
    }

    @Override
    public void onDisable() {
        //Your onDisable Code
    }

    public static CacheContainer getCacheContainer() {
        return cacheContainer;
    }
}
```

## Creating multiple instances

The creation of further instances is no problem, as all values are cached separately. This means that additional Cache-Container instances can be created without any problems in order to be able to use a separate instance for each Config-File as an example.


To create another instance, you need to do the same as in the previous step. It is **important** that the name is not the same as the name of another instance!

## Registration of data types

In order to fill a Cache-Container with values, the respective desired data types must first be registered so that they can be stored.
The registration of a data type can be done using the `cacheContainer#registerCacheType(DataType.class);` method.
The data type is always specified in the form of the class. So it is also possible to store each own data type in a Cache-Container.

In the following example, the String and Integer data types will be registered for the created Cache-Container-Instance:

```java
    private void registerDataTypes() {
        cacheContainer.registerCacheType(String.class);
        cacheContainer.registerCacheType(Integer.class);
    }
```

## Adding values to a Cache-Container
    
After the instance has been created and the respective data type has been registered, values can now be added. Each value is identified with a name so that the value can be returned later. A value can be added to a Cache-Container with the `cacheContainer#add(DataType.class, "CacheValueNameExample", "Example Value");` method.

???+ warning
    If a value with this name already exists, then the already stored value will be overwritten by the new value.

In the following example we add a total of 4 values to the Cache-Container, two different values per registered data type:

```java
    private void addCacheValues() {
        //Strings
        cacheContainer.add(String.class, "StringCacheValueNameExample", "Example Value");
        cacheContainer.add(String.class, "DifferentStringCacheValueName", "Different Value");

        //Integers
        cacheContainer.add(Integer.class, "IntegerCacheValueNameExample", 1);
        cacheContainer.add(Integer.class, "DifferentIntegerCacheValueName", 61);
    }
```

## Getting values from a Cache-Container

The output of stored values of a Cache-Container is very simple.
Values are stored per data type with a name and can thus be identified with it later at any time. For the output of values the `cacheContainer#get(DataType.class, "CacheValueNameExample");` method will be used.

In the following example, we send a message to the player that connects to the server using the PlayerJoinEvent. Here we refer to the string value named `StringCacheValueNameExample`which was added in the previous example:

```java
package de.tubeof.tubetils.usage.example.listener;

import de.tubeof.tubetils.api.cache.CacheContainer;
import de.tubeof.tubetils.usage.example.main.TubeTilsExample;
import org.bukkit.entity.Player;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.event.player.PlayerJoinEvent;

public class Join implements Listener {

    private final CacheContainer cacheContainer = TubeTilsExample.getCacheContainer();

    @EventHandler
    public void onJoin(PlayerJoinEvent event) {
        Player player = event.getPlayer();
        String welcomeMessage = (String) cacheContainer.get(String.class, "StringCacheValueNameExample");

        player.sendMessage(welcomeMessage);
    }
}
```
