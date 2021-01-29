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


To create another instance, you need to do the same as in the previous step. It is important that the name is not the same as the name of another instance!
