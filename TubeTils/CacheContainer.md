## What is a CacheContainer?

Cache

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
