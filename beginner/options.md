# Options

Once you've familiarized yourself with the [Quest Editor](../setup/quests-editor.md), you may be wondering about the 'Edit Options' selection. These are controls which apply _per-quest_, and are different than the settings in [config.yml](https://github.com/PikaMug/Quests/wiki/2-%E2%80%90-Configuration#configyml) which apply to _all_ quests.

![](https://camo.githubusercontent.com/01ac608458bd8b9ea686e4f66bb4d39e0131d0dd738a4317ba898f285345c08a/68747470733a2f2f692e696d6775722e636f6d2f7374485a504f752e706e67)

### General

| # | - | Choice                               | Description                                              |
| - | - | ------------------------------------ | -------------------------------------------------------- |
| 1 | - | Allow commands during quest          | Whether players may use commands after taking quest      |
| 2 | - | Allow quitting during quest          | Whether players may quit quest after accepting it        |
| 3 | - | Ignore blocks broken with Silk Touch | Whether break-block objectives count Silk Touch          |
| 4 | - | Ignore blocks replaced once broken   | Whether placing blocks decrements break-block objectives |

### Multiplayer

| # | - | Choice                         | Description                                                                                                        |
| - | - | ------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| 1 | - | Set provider via Unite         | Set integration with party plugin via [Unite](https://pikamug.gitbook.io/quests/beginner/dependencies#unite)       |
| 2 | - | Use Parties plugin             | Toggle integration with [Parties](https://github.com/PikaMug/Quests/wiki/Beginner-%E2%80%90-Dependencies#parties-) |
| 3 | - | Level of progress sharing      | How quest progress is distributed, see below                                                                       |
| 4 | - | Share with the same quest only | Whether players must have same quest to share progress                                                             |
| 5 | - | Maximum radial distance        | Distance between players for shared progress to count                                                              |
| 6 | - | Include offline players        | Whether to count shared progress for offline friends                                                               |

For level of progress sharing, the different values perform as follows:

1. Everything (default): constantly share progress. If one player breaks a block, all players break a block.
2. Objectives: if one player completes an objective, all members advance to the next objective.
3. Stages: if one player completes a stage, all members advance to the next stage.
4. Quests: similar to older versions' functionality. All members finish when one completes a quest.
