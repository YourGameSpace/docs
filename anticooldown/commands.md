Title: Commands

# Commands

Since v4, AntiCooldown has offered placeholders for the [PlaceholderAPI](https://www.spigotmc.org/resources/6245/) that show the current cooldown status.
Since AntiCooldown v4, there is also a player cooldown in addition to the world cooldown, which is controlled by permissions or the ItemRestriction module.

## /anticooldown

This is the main command of AntiCooldown, through which all other sub-commands can be executed

## /anticooldown help

This lists all commands incl. sub-commands of AntiCooldown to get an overview of the available commands.

## /anticooldown listDisabledWorlds

This lists all worlds that are currently deactivated, i.e. AntiCooldown does not make any changes in this world unless a player has the Bypass Permission.

## /anticooldown enableWorld

The command can be used to reactivate a world so that AntiCooldown will make changes again.

???+ info
    A name of the desired world can also be specified, otherwise the world in which the player is currently located is used.

## /anticooldown disableWorld

The command can be used to deactivate a world so that AntiCooldown no longer makes any changes.

???+ info
    A name of the desired world can also be specified, otherwise the world in which the player is currently located is used.
