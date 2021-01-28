Title: Cache-Container

## What is a Cache-Container?

In a Cache-Container, all kinds of values of the data types available in Java can be stored temporarily in order to be able to retrieve them at a later time.


This is very useful for Config-Files, among other things, so that IO-Resources can be saved and stored values from your Config-File can be retrieved quickly (much faster than getting data directly from the hard disk) and easily from the Cache-Container.

## Create a new instance

```java
package de.tubeof.tubetils.usage.example.main;

import de.tubeof.tubetils.api.cache.CacheContainer;
import org.bukkit.plugin.java.JavaPlugin;

public class TubeTileExample extends JavaPlugin {

    private static Object cacheContainer;

    @Override
    public void onLoad() {
        //Your onLoad Code
    }

    @Override
    public void onEnable() {
        //Your onEnable Code

        initCache();
    }

    @Override
    public void onDisable() {
        //Your onDisable Code
    }

    private void initCache() {
        cacheContainer = new CacheContainer("TubeTilsExample::VERSION-" + getDescription().getVersion() + "::01");
        getCacheContainer().registerCacheType(Integer.class);
        getCacheContainer().registerCacheType(Boolean.class);
        getCacheContainer().registerCacheType(String.class);
    }

    public static CacheContainer getCacheContainer() {
        return (CacheContainer) cacheContainer;
    }
}
```
