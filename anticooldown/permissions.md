Title: Permissions

# Permissions

Permissions are used by AntiCooldown mainly for commands, so only authorised players can use them and thus change settings.

Since AntiCooldown v4, it is also possible to activate general permissions support in the config, so that players need the permissions listed here for individual functions.

## Command-Permissions

|              Command             |       Type       |       Permission      |
|:--------------------------------:|:----------------:|:---------------------:|
|           /anticooldown          |   Main-Command   |           -           |
|        /anticooldown help        |   Help-Command   | anticooldown.settings |
| /anticooldown listDisabledWorlds | Info-Command     | anticooldown.settings |
| /anticooldown enableWorld        | Settings-Command | anticooldown.settings |
| /anticooldown disableWorld       | Settings-Command | anticooldown.settings |

## Feature-Permissions

???+ info
    **By default, it is not necessary to assign permissions!
    The assignment of permissions is only necessary if permission support has been activated in the Config.**

|       Feature      |                                                                                    Description                                                                                   |           Permission          |
|:------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-----------------------------:|
|  Cooldown Changes  | All types of cooldown changes. If permission support is enabled, it is required that the player has this permission, otherwise no cooldown change will be active for the player. |     anticooldown.cooldown     |
|    Combat Sounds   |                                                               This deactivates the new combat sounds for the player                                                              |   anticooldown.combatsounds   |
|    Sweep Attack    |                        This deactivates the sweep attack, which means that no other mobs in the vicinity suffer damage. It also deactivates the particles.                       |    anticooldown.sweepattack   |
| Custom Item Damage |            If the player is holding an item that has custom damage defined in the config, the damage of the item is overwritten with the damage defined in the config.           | anticooldown.customitemdamage |
