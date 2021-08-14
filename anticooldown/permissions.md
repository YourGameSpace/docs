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
