# GamerSafer Authentication plugin for Minecraft Java Edition servers. 

## Dependencies

- Java 16 or newer
- Paper 1.18.2+
- Velocity 1.18.2+
- Bungeecord 1.18.2+
- LuckPerms
- MySQL / MariaDB
- A open port to communicate with our API
- _Optional:_ ProtocolLib for onboarding room holograms.
- _Optional:_ PlaceholderAPI for placeholders.
- _Optional:_ Multiverse-Core to manage the onboarding room.
- _Optional:_ LiteBans to sync punishments.

## Commands

| Command                                                                                       | Description                                                 |
|-----------------------------------------------------------------------------------------------|-------------------------------------------------------------|
| /gsban (/ban)                                                                                 | Ban a player                                                |
| /gsbanip (/banip, /ipban, /gsipban)                                                           | Ban a player based on their IP                              |
| /gsbanlist (/banlist, /blist)                                                                 | Display the ban history of a player                         |
| /gscheck                                                                                      | Display the ALTs of a player                                |
| /gsdisable                                                                                    | Disable authentication checks                               |
| /gsenable                                                                                     | Enable authentication checks                                |
| /gsimport                                                                                     | Import punishments from another plugin (e.g.LiteBans)       |
| /gskick (/kick)                                                                               | Kick a player from the server                               |
| /gskicklist (/kicklist, /klist)                                                               | Display the kick history of a player                        |
| /gslink                                                                                       | Link the minecraft account to GamerSafer                    |
| /gsmute (/mute)                                                                               | Mute a player                                               |
| /gsmutelist (/mutelist, /mlist)                                                               | Display the mute history of a player                        |
| /gspreporthistory (/preporthistory, /playerhistory, /phistory, /phist, /preportlist, /prlist) | Display the punishment history of a player                  |
| /gsreload                                                                                     | Reload the configuration files                              |
| /gsreporthistory (/reporthistory, /history, /hist, /reportlist, /rlist)                       | Display the punishment history of a player                  |
| /gsroom                                                                                       | Teleport a player to the onboarding room                    |
| /gstempban (/tempban)                                                                         | Ban a player for a limited amount of time                   |
| /gstempbanip (/tempbanip, /iptempban, /gsiptempban)                                           | Ban a player for a limited amount of time based on their IP |
| /gstempmute (/tempmute)                                                                       | Mute a player for a limited amount of time                  |
| /gsunban (/unban)                                                                             | Unban a player                                              |
| /gsunbanip (/unbanip)                                                                         | Unban a player including IP based bans                      |
| /gsunmute (/unmute)                                                                           | Unmute a player                                             |
| /gsverify                                                                                     | Manually start the login process                            |
| /gswarn (/warn)                                                                               | Warn a player                                               |
| /gswarnlist (/warnlist, /wlist)                                                               | Display the warn history of a player                        |

## Permissions

| Permission                 | Description                                                                                                                                                                                 |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| gsauth.ban.list            | Access to /gsbanlist                                                                                                                                                                        |
| gsauth.ban.permanent       | Access to /gsban                                                                                                                                                                            |
| gsauth.ban.temporary       | Access to /gstempban                                                                                                                                                                        |
| gsauth.banip.permanent     | Access to /gsbanip                                                                                                                                                                          |
| gsauth.banip.temporary     | Access to /gstempbanip                                                                                                                                                                      |
| gsauth.check               | Access to /gscheck                                                                                                                                                                          |
| gsauth.check.age           | Display age group and age confidence in /gscheck                                                                                                                                            |
| gsauth.check.gsalts        | Display ALTs by guild member ID in /gscheck                                                                                                                                                 |
| gsauth.check.ipalts        | Display ALTs by IP address in /gscheck                                                                                                                                                      |
| gsauth.kick                | Access to /gskick                                                                                                                                                                           |
| gsauth.kick.list           | Access to /gskicklist                                                                                                                                                                       |
| gsauth.link                | Access to /gslink                                                                                                                                                                           |
| gsauth.link.other          | Allow to target other players with /gslink                                                                                                                                                  |
| gsauth.message.reminder    | Remind to authenticate with GamerSafer through a message                                                                                                                                    |
| gsauth.message.success     | Notify via message when they successfully authenticate with GamerSafer                                                                                                                      |
| gsauth.message.punishments | Notify via message when a player is punished                                                                                                                                                |
| gsauth.mute.list           | Access to /gsmutelist                                                                                                                                                                       |
| gsauth.mute.permanent      | Access to /gsmute                                                                                                                                                                           |
| gsauth.mute.temporary      | Access to /gstempmute                                                                                                                                                                       |
| gsauth.reload              | Access to /gsreload                                                                                                                                                                         |
| gsauth.report.history      | Access to /gsreporthistory                                                                                                                                                                  |
| gsauth.report.phistory     | Access to /gspreporthistory                                                                                                                                                                 |
| gsauth.room                | Access to /gsroom                                                                                                                                                                           |
| gsauth.room.other          | Allow to target other players wiht /gsroom                                                                                                                                                  |
| gsauth.unban               | Access to /gsunban                                                                                                                                                                          |
| gsauth.unbanip             | Access to /gsunbanip                                                                                                                                                                        |
| gsauth.unmute              | Access to /gsunmute                                                                                                                                                                         |
| gsauth.verifyplayer        | Access to /gsverify                                                                                                                                                                         |
| gsauth.warn                | Access to /gswarn                                                                                                                                                                           |
| gsauth.warn.list           | Access to /gswarnlist                                                                                                                                                                       |
| gsauth.age.chat.bypass     | Bypass the age group chat restrictions specified in player-preferences.yml                                                                                                                  |
| gamersafer.required.GROUP  | If a player has this permission they will be added to GROUP and all other groups are removed until the player successfully authenticates. A player can have multiple permissions like this. |

## Configuration

#### Onboarding Room

When configuring book pages for the onboarding room's lectern stand, you may use `<br>` in your page string to represent
a new line.

Throughout the onboarding configuration, you will encounter location strings. Location strings are in the format
of `X;Y;Z`, where `X`, `Y`, and `Z` are the desired coordinates. These may be integers (i.e. `1`) or decimal numbers (
i.e. `2.25`).
