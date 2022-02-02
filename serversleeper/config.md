Title: Config-Files

# Config-Files

ServerSleeper is fully adjustable by the user. Almost every detail can be changed through the config.

???+ info
    If anything is unclear, our [support](https://yourgamespace.com/support/) is always available!

## Config.yml

```yaml
# All messages of ServerSleeper
Messages:
  # Prefix for chat messages
  Prefix: §7[§cServerSleeper§7] §f
  # Message if a player try to use commands and has no permissions
  NoPerms: §cNo permissions!
  # Messages related to the toggle command
  ToggleSleep:
    # Message when then status was enabled
    Enabled: '§eServerSleeper was toggled. Current status: §aEnabled'
    # Message when then status was disabled
    Disabled: '§eServerSleeper was toggled. Current status: §cDisabled'
  # Message when a player tries to join and the sleep mode was enabled
  # Will only be used, if FastLogin is disabled
  LoginSleepEnabled: §cServer was in Sleep-Mode.%nPlease connect again, to join the
    server.
  # Message when a player tries to join and login delay is active
  # Will only be used, if FastLogin is disabled
  LoginDelayEnabled: §cThe server is waking up.%nPlease try again in few seconds.

# All settings of ServerSleeper
Settings:
  # Should FastLogin be enabled? (not recommended)
  # WARNING: Can cause issues for other plugins!
  # With FastLogin, players can connect directly to the server even if sleep mode is activated.
  # If FastLogin is disabled, the login is blocked the first time and the player has to connect again.
  # Available options: true, false
  FastLogin: false
  # Should the sleep mode be disabled when the server got pinged?
  # This means that when the status is requested from the server by the client in the server list.
  # Available options: true, false
  DisableSleepOnServerPing: false
  # Should the sleep mode be deactivated when a command is executed in the console?
  # Available options: true, false
  DisableSleepOnConsoleCommand: true
  # Should the sleep mode only be controlled via cronjobs?
  # The sleep mode is only activated or deactivated by the set cronjobs.
  # The sleep mode will no longer be activated automatically if there is no player on the server.
  # Available options: true, false
  UseOnlyCron: false

  # Settings related to tasks of ServerSleeper
  Tasks:
    # All settings of the ServerSleepControllerTask
    ServerSleepControllerTask:
      # The time in seconds to wait before checking if sleep mode can be activated after start-up.
      FirstPlayerCheckDelay: 30
      # Time in seconds at which the system should check whether sleep mode can be activated.
      PlayerCheckerDelay: 30
      # Should the ServerSleepControllerTask be stopped if sleep mode was started by a cronjob?
      # Available options: true, false
      DisableWhileCronjobRunning: true

    # All settings of the ServerSleepTask
    ServerSleepTask:
      # The strength of the sleep mode to be applied.
      # WARNING: The value should not be changed: Server crash possible!
      SleepingTimePerTick: 1200
      # Delay before players can join, after ServerSleepTask was disabled
      LoginTickDelayAfterStop: 120

  # Settings related to cronjobs
  Cronjobs:
    # Should cronjobs be activated?
    # Available options: true, false
    Enabled: false
    # Cronjobs, at which times the sleep mode should be activated.
    # Default: 10 p.m.; time zone of the server is used
    # Generator: https://www.freeformatter.com/cron-expression-generator-quartz.html
    EnableSleep:
    - 0 0 22 ? * * *
    # Cronjobs, at which times the sleep mode should be disabled.
    # Default: 8 a.m.; time zone of the server is used
    # Generator: https://www.freeformatter.com/cron-expression-generator-quartz.html
    DisableSleep:
    - 0 0 8 ? * * *

  # Settings related to the update checker
  Updates:
    # Should ServerSleeper check for updates?
    # Available options: true, false
    UseUpdateChecker: true
    # If there is an update, should this be output in the console?
    # Available options: true, false
    ConsoleNotify: true
    # If there is an update, should this be displayed to an admin when logging in?
    # Available options: true, false
    IngameNotify: true

# Version of the current config
# DO NOT CHANGE!
ConfigVersion: 9

```
