# Commands

- [Help Command](#help)
- [Administration](#administration)
- [Fun](#fun)
- [Music](#music)
- [Search](#search)
- [Utility](#utility)

<a name="introduction"></a>
## Introduction

This is the command reference for AvaIre. You can find more elaboration on each of the commands currently implemented here.

If you need for any further info, you can use the [help command](#help) for the bot to get info about command throttling limits, permission requirements and so forth. Got any questions? Check out #support in [AvaIre Central](#).

All commands uses the exclamation mark(!) as their prefix by default, you can change the prefix for all commands categories, or each category individually using the [!prefix](#ChangePrefixCommand) command.

<a name="HelpCommand"></a>
## Help Command

Displays a list of available command categories, commands in a given category, or information about a specific command.

#### Listing all categories

Using the help command with no additional arguments will display a list of all the categories.

    !help

#### Listing commands in category

Listing all commands in a category can be done by using the help command followed by the name of the category.

    !help <category>

> {tip} It is not required to type out the full name of the category, just typing a few characters will still list the commands in the category that starts with the given characters.<br>For example listing all the commands in the `Administration` category can be done by doing `!help a` for short.

#### Listing command information

Displaying a given command's information can be done by using `help` followed by the command you want to get information about.

    !help <command>

> {tip} Command aliases can be used as well, for example `!help sid` will display help for the `!serverid` command.

<a name="administration"></a>
## Administration

<a name="AddLevelRoleCommand"></a>
### Add Level Role Command

Adds a role to the leveling up table, roles on the table will be given to users once they level up and meet the requirements for the role.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.

 - [Level Hierarchy Command](#LevelHierarchyCommand)
 - [List Level Roles Command](#ListLevelRolesCommand)
 - [Remove Level Roles Command](#RemoveLevelRoleCommand)

#### Usage

	!alr <level requirement> <role>
	-  Adds to role to users when they level up and meet the level requirement.

#### Example

	!alr 5 Regular
	-  Adds the Regular role to the level up table, users who are level 5 and up will get the role when they level up.

<a name="AddSelfAssignableRoleCommand"></a>
### Add Self Assignable Role Command

Adds a role to the self-assignable roles list, any role on the list can be claimed by users when they use `:prefixiam <role>`.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.

 - [List Self Assignable Roles Command](#ListSelfAssignableRolesCommand)
 - [Remove Self Assignable Role Command](#RemoveSelfAssignableRoleCommand)

#### Usage

	!asar <role>
	-  Adds the mentioned role to the self-assignable roles list.

#### Example

	!asar DJ

<a name="AiCommand"></a>
### AI Command

Toggles the AI(Artificial Intelligence) on/off for the current channel.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.


#### Usage

	!ai
	-  Toggles the AI on/off for the current channel.


<a name="AliasCommand"></a>
### Alias Command

Creates and maps a custom alias for a pre-existing command. Provide no alias to remove an existing alias.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Aliases Command](#ListAliasesCommand)

#### Usage

	!alias <alias>
	-  Deletes the alias if it exists.
	!alias <alias> <command>
	-  Creates an alias for the given command.

#### Example

	!alias !ava !repeat **Website:** https://avairebot.com/

<a name="AutoAssignRoleCommand"></a>
### Autorole Command

Automatically assigns a specified role to every user who joins the server.

**Special permissions required to run this command**<br>The bot needs **Manage Roles** permission to run this command.<br>The user needs **Administrator** permission to run this command.


#### Usage

	!autorole
	-  Displays the current auto assignable role if one is set.
	!autorole <role>
	-  The role that should be auto assignable.
	!autorole disable
	-  Disables the auto assignable role.

#### Example

	!autorole @Member

<a name="BanCommand"></a>
### Ban Command

Bans the mentioned user from the server with the provided reason, all messages the user has sent in the last 7 days will also be deleted in the process, this action will be reported to any channel that has modloging enabled.

**Special permissions required to run this command**<br>The bot and the user needs the **Ban Members** permission to run this command.

 - [Soft Ban Command](#SoftBanCommand)
 - [Unban Command](#UnbanCommand)

#### Usage

	!ban <user> [reason]
	-  Bans the mentioned user with the given reason.
	!ban <user id> [reason]
	-  Bans the user with given ID and for the given reason.

#### Example

	!ban @Senither Spam and acting like a twat

<a name="CategoriesCommand"></a>
### Categories Command

Shows status of all command categories in the current or mentioned channel, both for globally and per-channel.


 - [Toggle Category Command](#ToggleCategoryCommand)
 - [Change Prefix Command](#ChangePrefixCommand)

#### Usage

	!categories [channel]
	-  Displays the status of the command categories in the mentioned channel, or the current channel if no channel was mentioned.

#### Example

	!categories #general

<a name="ChangePrefixCommand"></a>
### Change Prefix Command

Sets the prefix that should be used for all commands in a given category, if no prefix is provided the category prefix will be reset back to the default instead, each category in AvaIre can have a different prefix, or you can choose to change them all at the same time.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.

 - [Categories Command](#CategoriesCommand)
 - [Toggle Category Command](#ToggleCategoryCommand)

#### Usage

	!changeprefix <category>
	-  Resets the category prefix back to its default prefix.
	!changeprefix <category> [prefix]
	-  Sets the category prefix to the given prefix.

#### Example

	!changeprefix fun
	-  Resets the prefix back to default for the `fun` commands.
	!changeprefix admin /
	-  Sets the prefix to `/` for all admin commands.
	!changeprefix all a!
	-  Sets the prefix for all the categories to `a!`.

<a name="GoodbyeCommand"></a>
### Goodbye Command

Toggles the goodbye messages on or off for the current channel.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Goodbye Message Command](#GoodbyeMessageCommand)
 - [Welcome Command](#WelcomeCommand)
 - [Welcome Message Command](#WelcomeMessageCommand)

#### Usage

	!goodbye
	-  Toggles the goodbye messages on/off for the current channel


<a name="GoodbyeMessageCommand"></a>
### Goodbye Message Command

Sets the message that should be sent when a user leaves the server, this command can only be used if the goodbye module is enabled for the current channel.
The goodbye message has support for [placeholders](https://avairebot.com/docs/placeholders), allowing for customizing the message a bit more for each user.
https://avairebot.com/docs/placeholders

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Goodbye Command](#GoodbyeCommand)
 - [Welcome Command](#WelcomeCommand)
 - [Welcome Message Command](#WelcomeMessageCommand)

#### Usage

	!goodbyemessage
	-  Resets the goodbye back to the default message.
	!goodbyemessage <message>
	-  Sets the goodbye message to the given message.
	!goodbyemessage embed
	-  Disables embed messages.
	!goodbyemessage embed <color>
	-  Enables embed messages with the given color.
	!goodbyemessage <user>
	-  If a valid username, nickname or user was mentioned, an example message will be sent for the given user.

#### Example

	!goodbyemessage Goodbye %user%!
	-  Sets the message to "Goodbye @user".
	!goodbyemessage embed #ff0000
	-  Enables embed messages and sets it to red.
	!goodbyemessage @Senither
	-  Tests the goodbye message using the mentioned user.

<a name="IAmCommand"></a>
### I Am Command

Gives you the role with the given name if it is in the self-assignable list of roles.


 - [I Am Not Command](#IAmNotCommand)

#### Usage

	!iam <role>

#### Example

	!iam DJ

<a name="IAmNotCommand"></a>
### I Am Not Command

Removes the role with the given name from you if it is in the self-assignable list of roles.


 - [I Am Command](#IAmCommand)

#### Usage

	!iamnot <role>

#### Example

	!iamnot DJ

<a name="KickCommand"></a>
### Kick Command

Kicks the mentioned user from the server with the provided reason, this action will be reported to any channel that has modloging enabled.

**Special permissions required to run this command**<br>The bot and the user needs the **Kick Members** permission to run this command.

 - [Voice Kick Command](#VoiceKickCommand)

#### Usage

	!kick <user> [reason]
	-  Kicks the mentioned user with the given reason.

#### Example

	!kick @Senither Spamming things

<a name="LanguageCommand"></a>
### Language Command

Show a list of available languages or set a language that should be used for the server.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.


#### Usage

	!language [page]
	-  Displays a list of languages, 10 languages per page.
	!language [code]
	-  Sets the language to the given language code.

#### Example

	!language 2
	-  Displays the languages on page 2
	!language english
	-  Changes the language of the bot to English

<a name="LevelAlertsCommand"></a>
### Level Alerts Command

Toggles the Leveling alerts system on or off for the current server or channel.
This command requires the `Levels & Experience` feature to be enabled for the server!

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Level Hierarchy Command](#LevelHierarchyCommand)
 - [Level Modifier Command](#LevelModifierCommand)
 - [Toggle Level Command](#LevelCommand)
 - [Rank Command](#RankCommand)

#### Usage

	!levelalerts
	-  Toggles the level alerts feature on/off
	!levelalerts <channel>
	-  Toggles the level alerts feature on for the given channel

#### Example

	!levelalerts
	!levelalerts #general

<a name="LevelCommand"></a>
### Toggle Level Command

Toggles the Leveling system on or off for the current server.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Level Hierarchy Command](#LevelHierarchyCommand)
 - [Level Modifier Command](#LevelModifierCommand)
 - [Level Alerts Command](#LevelAlertsCommand)
 - [Rank Command](#RankCommand)

#### Usage

	!togglelevel
	-  Toggles the level feature on/off


<a name="LevelHierarchyCommand"></a>
### Level Hierarchy Command

Level Hierarchy determines if level roles give to users should be removed once they level up and get the next role, or if they should keep all of their roles, when the level hierarchy is enabled and a user levels up to get the next role, all other level roles they have will be removed, if they level up to a level without a level role, nothing will happen to them, the feature can be toggled on and off using this command.


 - [Add Level Role Command](#AddLevelRoleCommand)
 - [Remove Level Roles Command](#RemoveLevelRoleCommand)
 - [List Level Roles Command](#ListLevelRolesCommand)
 - [Level Modifier Command](#LevelModifierCommand)
 - [Level Alerts Command](#LevelAlertsCommand)
 - [Toggle Level Command](#LevelCommand)

#### Usage

	!levelhierarchy
	-  Displays the current level hierarchy status.
	!levelhierarchy <on/off>
	-  Toggles the feature on or off.

#### Example

	!levelhierarchy on
	-  Toggles the feature on.

<a name="LevelModifierCommand"></a>
### Level Modifier Command

The level modifier allows a server to set a custom level and experience modifier, allowing a server to fine tune the amount of XP required to level up by either making it harder or easier than default.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Level Hierarchy Command](#LevelHierarchyCommand)
 - [Level Alerts Command](#LevelAlertsCommand)
 - [Toggle Level Command](#LevelCommand)
 - [Rank Command](#RankCommand)

#### Usage

	!levelmodifier <percentage>
	-  Sets the level modifier to the given percentage.
	!levelmodifier reset
	-  Resets the level modifier back to the default value.

#### Example

	!levelmodifier 500%
	-  Sets the modifier to 500%
	!levelmodifier 0.01%
	-  Sets the modifier to 0.01%
	!levelmodifier reset
	-  Resets the modifier back to default.

<a name="ListAliasesCommand"></a>
### Aliases Command

Lists all the existing command aliases.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Alias Command](#AliasCommand)

#### Usage

	!aliases
	-  Lists all the aliases for the server.


<a name="ListLevelRolesCommand"></a>
### List Level Roles Command

List all the leveling roles and the level require to get them.


 - [Remove Level Roles Command](#RemoveLevelRoleCommand)
 - [Level Hierarchy Command](#LevelHierarchyCommand)
 - [Add Level Role Command](#AddLevelRoleCommand)

#### Usage

	!llr
	-  Lists all the roles you can get for leveling up.


<a name="ListSelfAssignableRolesCommand"></a>
### List Self Assignable Roles Command

List all the self-assignable roles, 10 per-page.


 - [Add Self Assignable Role Command](#AddSelfAssignableRoleCommand)
 - [Remove Self Assignable Role Command](#RemoveSelfAssignableRoleCommand)

#### Usage

	!lsar
	-  List all the self-assignable roles for the server.


<a name="ModlogCommand"></a>
### Modlog Command

Displays the modlogging status for the server if no arguments is given, you can also mention a text channel to enable modlogging and set it to the mentioned channel.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Modlog History Command](#ModlogHistoryCommand)
 - [Modlog Reason Command](#ModlogReasonCommand)

#### Usage

	!modlog
	-  Displays the current state of the modlog module for the server.
	!modlog <channel>
	-  Enabled modlogging and sets it to the mentioned channel.
	!modlog disable
	-  Disables the modlogging module for the server.

#### Example

	!modlog
	-  
	!modlog #modlog
	-  Enables modlogging and sets it to the modlog channel.
	!modlog disable
	-  Disables modlogging for the server.

<a name="ModlogHistoryCommand"></a>
### Modlog History Command

Displays the modlog history for the mentioned user, this will display all past warnings, bans, soft bans, kicks, and voice kicks.

**Special permissions required to run this command**<br>The user needs **Manage Messages** permission to run this command.

 - [Modlog Command](#ModlogCommand)
 - [Modlog Reason Command](#ModlogReasonCommand)

#### Usage

	!modloghistory <user>
	-  Displays the modlog history for the mentioned user.

#### Example

	!modloghistory @Senither
	-  Displays all the bad things Senither has done.

<a name="ModlogPardonCommand"></a>
### Pardon Command

Pardons the given modlog case ID, removing it from the users modlog history log and locking the message so it can't be edited.
Server admins can pardon any modlog cases, while everyone else can only pardon modlog cases they themselves are the cause for.

**Note:** This command does not revert the action for the modlog case, so if the user was banned, they will not be unbanned using this command.


 - [Modlog History Command](#ModlogHistoryCommand)
 - [Warn Command](#WarnCommand)
 - [Soft Ban Command](#SoftBanCommand)
 - [Ban Command](#BanCommand)
 - [Unban Command](#UnbanCommand)
 - [Kick Command](#KickCommand)
 - [Voice Kick Command](#VoiceKickCommand)

#### Usage

	!pardon <modlog id> [reason]
	-  Pardons the given modlog case ID with the given reason.

#### Example

	!pardon 9 Whoops, was a mistake

<a name="ModlogReasonCommand"></a>
### Modlog Reason Command

Sets the reason for an old modlog case, this command requires the server has a modlog channel set using the `b!modlog` command.
You can only set modlog reasons for old modlog cases if you were the moderator for the case.


 - [Modlog Command](#ModlogCommand)
 - [Modlog History Command](#ModlogHistoryCommand)

#### Usage

	!reason <case id> <reason>
	-  Sets the reason for the given ID

#### Example

	!reason 9 Advertising stuff in #general
	-  Sets the 9th modlog case to "Advertising stuff in #general"

<a name="NSFWCommand"></a>
### NSFW Command

Displays the NSFW status of the current channel, additionally on/off can be passed to the command to change the channels NSFW status.

**Special permissions required to run this command**<br>The bot and the user needs the **Manage Channels** permission to run this command.


#### Usage

	!nsfw
	-  Displays the NSFW status of the current channel.
	!nsfw <on | off>
	-  Changes the NSFW status of the current channel.
	!nsfw <channel>
	-  Displays the mentioned channels NSFW status
	!nsfw <channel> <on | off>
	-  Changes the NSFW status of the mentioned channel.

#### Example

	!nsfw
	!nsfw on
	!nsfw #nsfw-stuff
	!nsfw #general off

<a name="PurgeCommand"></a>
### Purge Command

Deletes up to 100 chat messages in any channel, you can mention a user if you only want to delete messages by the mentioned user.

**Special permissions required to run this command**<br>The user needs **Manage Messages** permission to run this command.<br>The bot needs **Manage Messages** and **Read History** permissions to run this command.


#### Usage

	!purge
	-  Deletes the last 5 messages.
	!purge [number]
	-  Deletes the given number of messages.
	!purge [number] [user]
	-  Deletes the given number of messages for the mentioned users.

#### Example

	!purge 56
	!purge 30 @Senither

<a name="RemoveLevelRoleCommand"></a>
### Remove Level Roles Command

Remove a role from the leveling up role table.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.

 - [Level Hierarchy Command](#LevelHierarchyCommand)
 - [List Level Roles Command](#ListLevelRolesCommand)
 - [Add Level Role Command](#AddLevelRoleCommand)

#### Usage

	!rlr <role>
	-  Removes the role from the leveling up role table.
	!rlr <level>
	-  Removes the role that is assigned to the given level from the role table.

#### Example

	!rlr Member
	!rlr 10

<a name="RemoveSelfAssignableRoleCommand"></a>
### Remove Self Assignable Role Command

Removes a role from the self-assignable roles list, any role on the list can be claimed by users when they use `:prefixiam <role>`.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.

 - [Add Self Assignable Role Command](#AddSelfAssignableRoleCommand)
 - [List Self Assignable Roles Command](#ListSelfAssignableRolesCommand)

#### Usage

	!rsar <role>
	-  Removes the mentioned role from the self-assignable roles list.

#### Example

	!rsar DJ

<a name="SlowmodeCommand"></a>
### Slowmode Command

Disables the slowmode or enables it with the given limit, users with the **Manage Messages**  or **Manage Channels** permissions are exempt from slowmode limits.

**Special permissions required to run this command**<br>The bot and the user needs the **Manage Channels** permission to run this command.

 - [Purge Command](#PurgeCommand)

#### Usage

	!slowmode [channel] <off>
	-  Disables slowmode for the current channel.
	!slowmode [channel] <seconds>
	-  Enables slowmode, allowing one message per user every given second.

#### Example

	!slowmode off
	-  Disables slowmode.
	!slowmode #general off
	-  Disables slowmode in the general channel.
	!slowmode 5
	-  Enables slowmode, allowing one message every five seconds.
	!slowmode #slow-chat 30
	-  Enables slowmode in the slow chat channel, allowing one message every 30 seconds per user.

<a name="SoftBanCommand"></a>
### Soft Ban Command

Bans the mentioned user from the server with the provided reason without removing any of the messages they have sent, this action will be reported to any channel that has modloging enabled.

**Special permissions required to run this command**<br>The bot and the user needs the **Ban Members** permission to run this command.

 - [Unban Command](#UnbanCommand)
 - [Ban Command](#BanCommand)

#### Usage

	!softban <user> [reason]
	-  Bans the mentioned user with the given reason.
	!softban <user id> [reason]
	-  Bans the user with given ID and for the given reason.

#### Example

	!softban @Senither Being a potato

<a name="ToggleCategoryCommand"></a>
### Toggle Category Command

This command allows you to toggle command categories on/off for the current channel or the whole server in one go, this is useful if you like some features in the bot but not others.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.

 - [Categories Command](#CategoriesCommand)
 - [Change Prefix Command](#ChangePrefixCommand)

#### Usage

	!togglecategory <category> <channel/global> [status]
	-  Changes the command category status for the mentioned channel or globally if specified.

#### Example

	!togglecategory fun global off
	-  Disables all the fun on the server D:
	!togglecategory util #general off
	-  Disables all the utility commands in the general channel.

<a name="UnbanCommand"></a>
### Unban Command

Unbans the user with the given ID from the server if they are banned, if a modlog channel is setup, the unban will be logged to the channel as well.

**Special permissions required to run this command**<br>The bot and the user needs the **Ban Members** permission to run this command.

 - [Soft Ban Command](#SoftBanCommand)
 - [Ban Command](#BanCommand)

#### Usage

	!unban <user id> [reason]
	-  Unbans the user with given ID and for the given reason.

#### Example

	!unban 88739639380172800 Wasn't actually a twat

<a name="VoiceKickCommand"></a>
### Voice Kick Command

Kicks the mentioned user from the voice channel they're currently connected to, this action will be reported to any channel that has modloging enabled.

**Special permissions required to run this command**<br>The user needs **Kick Members** permission to run this command.<br>The bot needs **Manage Channels** and **Move Members** permissions to run this command.

 - [Kick Command](#KickCommand)

#### Usage

	!voicekick <user> [reason]
	-  Kicks the mentioned user with the given reason.

#### Example

	!voicekick @Senither Yelling at people

<a name="WarnCommand"></a>
### Warn Command

Warns a given user with a message, this action will be reported to any channel that has modloging enabled.

**Special permissions required to run this command**<br>The user needs **Manage Messages** permission to run this command.

 - [Modlog History Command](#ModlogHistoryCommand)
 - [Modlog Reason Command](#ModlogReasonCommand)

#### Usage

	!warn <user> [reason]
	-  Warns the mentioned user with the given reason.

#### Example

	!warn @Senither Being a potato
	-  Warns Senither for being a potato.

<a name="WelcomeCommand"></a>
### Welcome Command

Toggles the welcome messages on or off for the current channel.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Goodbye Command](#GoodbyeCommand)
 - [Goodbye Message Command](#GoodbyeMessageCommand)
 - [Welcome Message Command](#WelcomeMessageCommand)

#### Usage

	!welcome
	-  Toggles the welcome messages on/off for the current channel


<a name="WelcomeMessageCommand"></a>
### Welcome Message Command

Sets the message that should be sent when a user joins the server, this command can only be used if the welcome module is enabled for the current channel.
The welcome message has support for [placeholders](https://avairebot.com/docs/placeholders), allowing for customizing the message a bit more for each user.
https://avairebot.com/docs/placeholders

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Goodbye Command](#GoodbyeCommand)
 - [Goodbye Message Command](#GoodbyeMessageCommand)
 - [Welcome Command](#WelcomeCommand)

#### Usage

	!welcomemessage
	-  Resets the welcome message back to the default message.
	!welcomemessage <message>
	-  Sets the welcome message to the given message.
	!welcomemessage embed
	-  Disables embed messages.
	!welcomemessage embed <color>
	-  Enables embed messages with the given color.
	!welcomemessage <user>
	-  If a valid username, nickname or user was mentioned, an example message will be sent for the given user.

#### Example

	!welcomemessage Welcome %user%!
	-  Sets the message to "Welcome @user".
	!welcomemessage embed #ff0000
	-  Enables embed messages and sets it to red.
	!welcomemessage @Senither
	-  Tests the welcome message using the mentioned user.


<a name="administration"></a>
## Administration

<a name="AddLevelRoleCommand"></a>
### Add Level Role Command

Adds a role to the leveling up table, roles on the table will be given to users once they level up and meet the requirements for the role.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.

 - [Level Hierarchy Command](#LevelHierarchyCommand)
 - [List Level Roles Command](#ListLevelRolesCommand)
 - [Remove Level Roles Command](#RemoveLevelRoleCommand)

#### Usage

	!alr <level requirement> <role>
	-  Adds to role to users when they level up and meet the level requirement.

#### Example

	!alr 5 Regular
	-  Adds the Regular role to the level up table, users who are level 5 and up will get the role when they level up.

<a name="AddSelfAssignableRoleCommand"></a>
### Add Self Assignable Role Command

Adds a role to the self-assignable roles list, any role on the list can be claimed by users when they use `:prefixiam <role>`.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.

 - [List Self Assignable Roles Command](#ListSelfAssignableRolesCommand)
 - [Remove Self Assignable Role Command](#RemoveSelfAssignableRoleCommand)

#### Usage

	!asar <role>
	-  Adds the mentioned role to the self-assignable roles list.

#### Example

	!asar DJ

<a name="AiCommand"></a>
### AI Command

Toggles the AI(Artificial Intelligence) on/off for the current channel.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.


#### Usage

	!ai
	-  Toggles the AI on/off for the current channel.


<a name="AliasCommand"></a>
### Alias Command

Creates and maps a custom alias for a pre-existing command. Provide no alias to remove an existing alias.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Aliases Command](#ListAliasesCommand)

#### Usage

	!alias <alias>
	-  Deletes the alias if it exists.
	!alias <alias> <command>
	-  Creates an alias for the given command.

#### Example

	!alias !ava !repeat **Website:** https://avairebot.com/

<a name="AutoAssignRoleCommand"></a>
### Autorole Command

Automatically assigns a specified role to every user who joins the server.

**Special permissions required to run this command**<br>The bot needs **Manage Roles** permission to run this command.<br>The user needs **Administrator** permission to run this command.


#### Usage

	!autorole
	-  Displays the current auto assignable role if one is set.
	!autorole <role>
	-  The role that should be auto assignable.
	!autorole disable
	-  Disables the auto assignable role.

#### Example

	!autorole @Member

<a name="BanCommand"></a>
### Ban Command

Bans the mentioned user from the server with the provided reason, all messages the user has sent in the last 7 days will also be deleted in the process, this action will be reported to any channel that has modloging enabled.

**Special permissions required to run this command**<br>The bot and the user needs the **Ban Members** permission to run this command.

 - [Soft Ban Command](#SoftBanCommand)
 - [Unban Command](#UnbanCommand)

#### Usage

	!ban <user> [reason]
	-  Bans the mentioned user with the given reason.
	!ban <user id> [reason]
	-  Bans the user with given ID and for the given reason.

#### Example

	!ban @Senither Spam and acting like a twat

<a name="CategoriesCommand"></a>
### Categories Command

Shows status of all command categories in the current or mentioned channel, both for globally and per-channel.


 - [Toggle Category Command](#ToggleCategoryCommand)
 - [Change Prefix Command](#ChangePrefixCommand)

#### Usage

	!categories [channel]
	-  Displays the status of the command categories in the mentioned channel, or the current channel if no channel was mentioned.

#### Example

	!categories #general

<a name="ChangePrefixCommand"></a>
### Change Prefix Command

Sets the prefix that should be used for all commands in a given category, if no prefix is provided the category prefix will be reset back to the default instead, each category in AvaIre can have a different prefix, or you can choose to change them all at the same time.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.

 - [Categories Command](#CategoriesCommand)
 - [Toggle Category Command](#ToggleCategoryCommand)

#### Usage

	!changeprefix <category>
	-  Resets the category prefix back to its default prefix.
	!changeprefix <category> [prefix]
	-  Sets the category prefix to the given prefix.

#### Example

	!changeprefix fun
	-  Resets the prefix back to default for the `fun` commands.
	!changeprefix admin /
	-  Sets the prefix to `/` for all admin commands.
	!changeprefix all a!
	-  Sets the prefix for all the categories to `a!`.

<a name="GoodbyeCommand"></a>
### Goodbye Command

Toggles the goodbye messages on or off for the current channel.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Goodbye Message Command](#GoodbyeMessageCommand)
 - [Welcome Command](#WelcomeCommand)
 - [Welcome Message Command](#WelcomeMessageCommand)

#### Usage

	!goodbye
	-  Toggles the goodbye messages on/off for the current channel


<a name="GoodbyeMessageCommand"></a>
### Goodbye Message Command

Sets the message that should be sent when a user leaves the server, this command can only be used if the goodbye module is enabled for the current channel.
The goodbye message has support for [placeholders](https://avairebot.com/docs/placeholders), allowing for customizing the message a bit more for each user.
https://avairebot.com/docs/placeholders

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Goodbye Command](#GoodbyeCommand)
 - [Welcome Command](#WelcomeCommand)
 - [Welcome Message Command](#WelcomeMessageCommand)

#### Usage

	!goodbyemessage
	-  Resets the goodbye back to the default message.
	!goodbyemessage <message>
	-  Sets the goodbye message to the given message.
	!goodbyemessage embed
	-  Disables embed messages.
	!goodbyemessage embed <color>
	-  Enables embed messages with the given color.
	!goodbyemessage <user>
	-  If a valid username, nickname or user was mentioned, an example message will be sent for the given user.

#### Example

	!goodbyemessage Goodbye %user%!
	-  Sets the message to "Goodbye @user".
	!goodbyemessage embed #ff0000
	-  Enables embed messages and sets it to red.
	!goodbyemessage @Senither
	-  Tests the goodbye message using the mentioned user.

<a name="IAmCommand"></a>
### I Am Command

Gives you the role with the given name if it is in the self-assignable list of roles.


 - [I Am Not Command](#IAmNotCommand)

#### Usage

	!iam <role>

#### Example

	!iam DJ

<a name="IAmNotCommand"></a>
### I Am Not Command

Removes the role with the given name from you if it is in the self-assignable list of roles.


 - [I Am Command](#IAmCommand)

#### Usage

	!iamnot <role>

#### Example

	!iamnot DJ

<a name="KickCommand"></a>
### Kick Command

Kicks the mentioned user from the server with the provided reason, this action will be reported to any channel that has modloging enabled.

**Special permissions required to run this command**<br>The bot and the user needs the **Kick Members** permission to run this command.

 - [Voice Kick Command](#VoiceKickCommand)

#### Usage

	!kick <user> [reason]
	-  Kicks the mentioned user with the given reason.

#### Example

	!kick @Senither Spamming things

<a name="LanguageCommand"></a>
### Language Command

Show a list of available languages or set a language that should be used for the server.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.


#### Usage

	!language [page]
	-  Displays a list of languages, 10 languages per page.
	!language [code]
	-  Sets the language to the given language code.

#### Example

	!language 2
	-  Displays the languages on page 2
	!language english
	-  Changes the language of the bot to English

<a name="LevelAlertsCommand"></a>
### Level Alerts Command

Toggles the Leveling alerts system on or off for the current server or channel.
This command requires the `Levels & Experience` feature to be enabled for the server!

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Level Hierarchy Command](#LevelHierarchyCommand)
 - [Level Modifier Command](#LevelModifierCommand)
 - [Toggle Level Command](#LevelCommand)
 - [Rank Command](#RankCommand)

#### Usage

	!levelalerts
	-  Toggles the level alerts feature on/off
	!levelalerts <channel>
	-  Toggles the level alerts feature on for the given channel

#### Example

	!levelalerts
	!levelalerts #general

<a name="LevelCommand"></a>
### Toggle Level Command

Toggles the Leveling system on or off for the current server.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Level Hierarchy Command](#LevelHierarchyCommand)
 - [Level Modifier Command](#LevelModifierCommand)
 - [Level Alerts Command](#LevelAlertsCommand)
 - [Rank Command](#RankCommand)

#### Usage

	!togglelevel
	-  Toggles the level feature on/off


<a name="LevelHierarchyCommand"></a>
### Level Hierarchy Command

Level Hierarchy determines if level roles give to users should be removed once they level up and get the next role, or if they should keep all of their roles, when the level hierarchy is enabled and a user levels up to get the next role, all other level roles they have will be removed, if they level up to a level without a level role, nothing will happen to them, the feature can be toggled on and off using this command.


 - [Add Level Role Command](#AddLevelRoleCommand)
 - [Remove Level Roles Command](#RemoveLevelRoleCommand)
 - [List Level Roles Command](#ListLevelRolesCommand)
 - [Level Modifier Command](#LevelModifierCommand)
 - [Level Alerts Command](#LevelAlertsCommand)
 - [Toggle Level Command](#LevelCommand)

#### Usage

	!levelhierarchy
	-  Displays the current level hierarchy status.
	!levelhierarchy <on/off>
	-  Toggles the feature on or off.

#### Example

	!levelhierarchy on
	-  Toggles the feature on.

<a name="LevelModifierCommand"></a>
### Level Modifier Command

The level modifier allows a server to set a custom level and experience modifier, allowing a server to fine tune the amount of XP required to level up by either making it harder or easier than default.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Level Hierarchy Command](#LevelHierarchyCommand)
 - [Level Alerts Command](#LevelAlertsCommand)
 - [Toggle Level Command](#LevelCommand)
 - [Rank Command](#RankCommand)

#### Usage

	!levelmodifier <percentage>
	-  Sets the level modifier to the given percentage.
	!levelmodifier reset
	-  Resets the level modifier back to the default value.

#### Example

	!levelmodifier 500%
	-  Sets the modifier to 500%
	!levelmodifier 0.01%
	-  Sets the modifier to 0.01%
	!levelmodifier reset
	-  Resets the modifier back to default.

<a name="ListAliasesCommand"></a>
### Aliases Command

Lists all the existing command aliases.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Alias Command](#AliasCommand)

#### Usage

	!aliases
	-  Lists all the aliases for the server.


<a name="ListLevelRolesCommand"></a>
### List Level Roles Command

List all the leveling roles and the level require to get them.


 - [Remove Level Roles Command](#RemoveLevelRoleCommand)
 - [Level Hierarchy Command](#LevelHierarchyCommand)
 - [Add Level Role Command](#AddLevelRoleCommand)

#### Usage

	!llr
	-  Lists all the roles you can get for leveling up.


<a name="ListSelfAssignableRolesCommand"></a>
### List Self Assignable Roles Command

List all the self-assignable roles, 10 per-page.


 - [Add Self Assignable Role Command](#AddSelfAssignableRoleCommand)
 - [Remove Self Assignable Role Command](#RemoveSelfAssignableRoleCommand)

#### Usage

	!lsar
	-  List all the self-assignable roles for the server.


<a name="ModlogCommand"></a>
### Modlog Command

Displays the modlogging status for the server if no arguments is given, you can also mention a text channel to enable modlogging and set it to the mentioned channel.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Modlog History Command](#ModlogHistoryCommand)
 - [Modlog Reason Command](#ModlogReasonCommand)

#### Usage

	!modlog
	-  Displays the current state of the modlog module for the server.
	!modlog <channel>
	-  Enabled modlogging and sets it to the mentioned channel.
	!modlog disable
	-  Disables the modlogging module for the server.

#### Example

	!modlog
	-  
	!modlog #modlog
	-  Enables modlogging and sets it to the modlog channel.
	!modlog disable
	-  Disables modlogging for the server.

<a name="ModlogHistoryCommand"></a>
### Modlog History Command

Displays the modlog history for the mentioned user, this will display all past warnings, bans, soft bans, kicks, and voice kicks.

**Special permissions required to run this command**<br>The user needs **Manage Messages** permission to run this command.

 - [Modlog Command](#ModlogCommand)
 - [Modlog Reason Command](#ModlogReasonCommand)

#### Usage

	!modloghistory <user>
	-  Displays the modlog history for the mentioned user.

#### Example

	!modloghistory @Senither
	-  Displays all the bad things Senither has done.

<a name="ModlogPardonCommand"></a>
### Pardon Command

Pardons the given modlog case ID, removing it from the users modlog history log and locking the message so it can't be edited.
Server admins can pardon any modlog cases, while everyone else can only pardon modlog cases they themselves are the cause for.

**Note:** This command does not revert the action for the modlog case, so if the user was banned, they will not be unbanned using this command.


 - [Modlog History Command](#ModlogHistoryCommand)
 - [Warn Command](#WarnCommand)
 - [Soft Ban Command](#SoftBanCommand)
 - [Ban Command](#BanCommand)
 - [Unban Command](#UnbanCommand)
 - [Kick Command](#KickCommand)
 - [Voice Kick Command](#VoiceKickCommand)

#### Usage

	!pardon <modlog id> [reason]
	-  Pardons the given modlog case ID with the given reason.

#### Example

	!pardon 9 Whoops, was a mistake

<a name="ModlogReasonCommand"></a>
### Modlog Reason Command

Sets the reason for an old modlog case, this command requires the server has a modlog channel set using the `b!modlog` command.
You can only set modlog reasons for old modlog cases if you were the moderator for the case.


 - [Modlog Command](#ModlogCommand)
 - [Modlog History Command](#ModlogHistoryCommand)

#### Usage

	!reason <case id> <reason>
	-  Sets the reason for the given ID

#### Example

	!reason 9 Advertising stuff in #general
	-  Sets the 9th modlog case to "Advertising stuff in #general"

<a name="NSFWCommand"></a>
### NSFW Command

Displays the NSFW status of the current channel, additionally on/off can be passed to the command to change the channels NSFW status.

**Special permissions required to run this command**<br>The bot and the user needs the **Manage Channels** permission to run this command.


#### Usage

	!nsfw
	-  Displays the NSFW status of the current channel.
	!nsfw <on | off>
	-  Changes the NSFW status of the current channel.
	!nsfw <channel>
	-  Displays the mentioned channels NSFW status
	!nsfw <channel> <on | off>
	-  Changes the NSFW status of the mentioned channel.

#### Example

	!nsfw
	!nsfw on
	!nsfw #nsfw-stuff
	!nsfw #general off

<a name="PurgeCommand"></a>
### Purge Command

Deletes up to 100 chat messages in any channel, you can mention a user if you only want to delete messages by the mentioned user.

**Special permissions required to run this command**<br>The user needs **Manage Messages** permission to run this command.<br>The bot needs **Manage Messages** and **Read History** permissions to run this command.


#### Usage

	!purge
	-  Deletes the last 5 messages.
	!purge [number]
	-  Deletes the given number of messages.
	!purge [number] [user]
	-  Deletes the given number of messages for the mentioned users.

#### Example

	!purge 56
	!purge 30 @Senither

<a name="RemoveLevelRoleCommand"></a>
### Remove Level Roles Command

Remove a role from the leveling up role table.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.

 - [Level Hierarchy Command](#LevelHierarchyCommand)
 - [List Level Roles Command](#ListLevelRolesCommand)
 - [Add Level Role Command](#AddLevelRoleCommand)

#### Usage

	!rlr <role>
	-  Removes the role from the leveling up role table.
	!rlr <level>
	-  Removes the role that is assigned to the given level from the role table.

#### Example

	!rlr Member
	!rlr 10

<a name="RemoveSelfAssignableRoleCommand"></a>
### Remove Self Assignable Role Command

Removes a role from the self-assignable roles list, any role on the list can be claimed by users when they use `:prefixiam <role>`.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.

 - [Add Self Assignable Role Command](#AddSelfAssignableRoleCommand)
 - [List Self Assignable Roles Command](#ListSelfAssignableRolesCommand)

#### Usage

	!rsar <role>
	-  Removes the mentioned role from the self-assignable roles list.

#### Example

	!rsar DJ

<a name="SlowmodeCommand"></a>
### Slowmode Command

Disables the slowmode or enables it with the given limit, users with the **Manage Messages**  or **Manage Channels** permissions are exempt from slowmode limits.

**Special permissions required to run this command**<br>The bot and the user needs the **Manage Channels** permission to run this command.

 - [Purge Command](#PurgeCommand)

#### Usage

	!slowmode [channel] <off>
	-  Disables slowmode for the current channel.
	!slowmode [channel] <seconds>
	-  Enables slowmode, allowing one message per user every given second.

#### Example

	!slowmode off
	-  Disables slowmode.
	!slowmode #general off
	-  Disables slowmode in the general channel.
	!slowmode 5
	-  Enables slowmode, allowing one message every five seconds.
	!slowmode #slow-chat 30
	-  Enables slowmode in the slow chat channel, allowing one message every 30 seconds per user.

<a name="SoftBanCommand"></a>
### Soft Ban Command

Bans the mentioned user from the server with the provided reason without removing any of the messages they have sent, this action will be reported to any channel that has modloging enabled.

**Special permissions required to run this command**<br>The bot and the user needs the **Ban Members** permission to run this command.

 - [Unban Command](#UnbanCommand)
 - [Ban Command](#BanCommand)

#### Usage

	!softban <user> [reason]
	-  Bans the mentioned user with the given reason.
	!softban <user id> [reason]
	-  Bans the user with given ID and for the given reason.

#### Example

	!softban @Senither Being a potato

<a name="ToggleCategoryCommand"></a>
### Toggle Category Command

This command allows you to toggle command categories on/off for the current channel or the whole server in one go, this is useful if you like some features in the bot but not others.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.

 - [Categories Command](#CategoriesCommand)
 - [Change Prefix Command](#ChangePrefixCommand)

#### Usage

	!togglecategory <category> <channel/global> [status]
	-  Changes the command category status for the mentioned channel or globally if specified.

#### Example

	!togglecategory fun global off
	-  Disables all the fun on the server D:
	!togglecategory util #general off
	-  Disables all the utility commands in the general channel.

<a name="UnbanCommand"></a>
### Unban Command

Unbans the user with the given ID from the server if they are banned, if a modlog channel is setup, the unban will be logged to the channel as well.

**Special permissions required to run this command**<br>The bot and the user needs the **Ban Members** permission to run this command.

 - [Soft Ban Command](#SoftBanCommand)
 - [Ban Command](#BanCommand)

#### Usage

	!unban <user id> [reason]
	-  Unbans the user with given ID and for the given reason.

#### Example

	!unban 88739639380172800 Wasn't actually a twat

<a name="VoiceKickCommand"></a>
### Voice Kick Command

Kicks the mentioned user from the voice channel they're currently connected to, this action will be reported to any channel that has modloging enabled.

**Special permissions required to run this command**<br>The user needs **Kick Members** permission to run this command.<br>The bot needs **Manage Channels** and **Move Members** permissions to run this command.

 - [Kick Command](#KickCommand)

#### Usage

	!voicekick <user> [reason]
	-  Kicks the mentioned user with the given reason.

#### Example

	!voicekick @Senither Yelling at people

<a name="WarnCommand"></a>
### Warn Command

Warns a given user with a message, this action will be reported to any channel that has modloging enabled.

**Special permissions required to run this command**<br>The user needs **Manage Messages** permission to run this command.

 - [Modlog History Command](#ModlogHistoryCommand)
 - [Modlog Reason Command](#ModlogReasonCommand)

#### Usage

	!warn <user> [reason]
	-  Warns the mentioned user with the given reason.

#### Example

	!warn @Senither Being a potato
	-  Warns Senither for being a potato.

<a name="WelcomeCommand"></a>
### Welcome Command

Toggles the welcome messages on or off for the current channel.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Goodbye Command](#GoodbyeCommand)
 - [Goodbye Message Command](#GoodbyeMessageCommand)
 - [Welcome Message Command](#WelcomeMessageCommand)

#### Usage

	!welcome
	-  Toggles the welcome messages on/off for the current channel


<a name="WelcomeMessageCommand"></a>
### Welcome Message Command

Sets the message that should be sent when a user joins the server, this command can only be used if the welcome module is enabled for the current channel.
The welcome message has support for [placeholders](https://avairebot.com/docs/placeholders), allowing for customizing the message a bit more for each user.
https://avairebot.com/docs/placeholders

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.

 - [Goodbye Command](#GoodbyeCommand)
 - [Goodbye Message Command](#GoodbyeMessageCommand)
 - [Welcome Command](#WelcomeCommand)

#### Usage

	!welcomemessage
	-  Resets the welcome message back to the default message.
	!welcomemessage <message>
	-  Sets the welcome message to the given message.
	!welcomemessage embed
	-  Disables embed messages.
	!welcomemessage embed <color>
	-  Enables embed messages with the given color.
	!welcomemessage <user>
	-  If a valid username, nickname or user was mentioned, an example message will be sent for the given user.

#### Example

	!welcomemessage Welcome %user%!
	-  Sets the message to "Welcome @user".
	!welcomemessage embed #ff0000
	-  Enables embed messages and sets it to red.
	!welcomemessage @Senither
	-  Tests the welcome message using the mentioned user.


<a name="fun"></a>
## Fun

<a name="ChuckNorrisCommand"></a>
### Chuck Norris Command

I will get a random 100% true, real facts about Chuck Norris for you using the "Internet Chuck Norris Database".



#### Usage

	!chucknorris [name]
	-  Gets a random fact for you, if a name is given "Chuck Norris" will be replaced with the given name.

#### Example

	!chucknorris @Senither

<a name="CoinflipCommand"></a>
### Coinflip Command

Flips a coin heads or tails.



#### Usage

	!coinflip
	-  Flips a coin for either heads or tails.


<a name="DiceCommand"></a>
### Dice Command

Rolls a dice or multiple dice with the given number of sides.



#### Usage

	!dice <dice followed by a D and the sides>
	-  Rolls some dice randomly

#### Example

	!dice 4D8 2D4

<a name="EightBallCommand"></a>
### Eight Ball Command

Ask 8Ball a question and get a random response back.



#### Usage

	!8ball <question>

#### Example

	!8ball will i have a good day today?

<a name="FlipTextCommand"></a>
### Flip Text Command

Flips the given message upside down.



#### Usage

	!flip <message>
	-  Flips the given message.

#### Example

	!flip This is some random message

<a name="LennyCommand"></a>
### Lenny command

( ͡° ͜ʖ ͡°)



#### Usage

	!lenny
	-  ( ͡° ͜ʖ ͡°)

#### Example

	( ͡° ͜ʖ ͡°)

<a name="MemeCommand"></a>
### Meme Command

Generates memes with your given text, you can tag users to use their avatar as a meme, or just give the meme name you wanna use.



#### Usage

	!meme list
	-  Lists all the available meme types.
	!meme <meme> <top text> <bottom text>
	-  Generates the meme with the given text.
	!meme <user> <top text> <bottom text>
	-  Generates a meme with the tagged users avatar and the given text.

#### Example

	!meme buzz "Memes" "Memes everywhere"
	!meme @Senither "Creates a Meme command for AvaIre" "Almost no one uses it"

<a name="RandomCatCommand"></a>
### Random Cat Command

I will scour the internet to find a random cat picture for you.


 - [Random Dog Command](#RandomDogCommand)

#### Usage

	!randomcat
	-  Gets a random picture of a cat and sends it in the channel.


<a name="RandomDogCommand"></a>
### Random Dog Command

I will scour the internet to find a random dog picture for you.


 - [Random Cat Command](#RandomCatCommand)

#### Usage

	!randomdog
	-  Gets a random picture of a dog and sends it in the channel.


<a name="RepeatCommand"></a>
### Repeat Command

I will repeat anything you say.



#### Usage

	!repeat <message>
	-  Repeats the given message

#### Example

	!repeat I am a BOT

<a name="ReverseCommand"></a>
### Reverse Command

Reverses the message given.



#### Usage

	!reverse <message>
	-  Reverses the given message.

#### Example

	!reverse This is some random message

<a name="RipCommand"></a>
### RIP Command

Pay your respects



#### Usage

	!rip
	-  Pay your respects


<a name="RollCommand"></a>
### Roll Command

Roll a random number between 1 and 100, or within the given parameters.



#### Usage

	!roll
	!roll [max]
	!roll [min] [max]

#### Example

	!roll 3 6

<a name="SayCommand"></a>
### Say Command

I will say whatever you tell me to.

**Special permissions required to run this command**<br>The bot and the user needs the **Manage Messages** permission to run this command.


#### Usage

	!say <message>
	-  Makes the bot say the given message

#### Example

	!say I am a BOT

<a name="UndertaleTextBoxCommand"></a>
### Undertale TextBox Command

Create your own Undertale text boxes with any character and text you want, you can also specify a image through a URL that should be used as the avatar instead.!
Generator owned by [Demirramon](https://demirramon.com/). Undertale owned by Toby Fox. All rights reserved.



#### Usage

	!undertale list [page]
	-  Lists some undertale characters the generator supports.
	!undertale <url> <message>
	-  Generates the image using the given image url and message.
	!undertale <character> <message>
	-  Generates the image using the provided undertale character as the avatar, and the provided message.

#### Example

	!undertale Toriel Greetings, my child
	!undertale https://i.imgur.com/ZupgGkI.jpg Want to play?


<a name="music"></a>
## Music

<a name="ClearQueueCommand"></a>
### Clear Music Queue Command

Clears the music queue of all pending songs



#### Usage

	!clearqueue
	-  Clears the music queue


<a name="DJLevelCommand"></a>
### DJ Level Command

Change the DJ level requirement for the server, this changes what music commands people can use with or without the `DJ` Discord role.

**Special permissions required to run this command**<br>The user needs **Manage Server** permission to run this command.


#### Usage

	!djlevel
	-  Displays the current DJ Level for the server.
	!djlevel types
	-  Displays all the types and some info about them.
	!djlevel <type>
	-  Change the DJ Level to the given type.

#### Example

	!djlevel types
	-  Displays all the types and info about them.
	!djlevel normal
	-  Changes the DJ Level to "normal".

<a name="MoveHereCommand"></a>
### Move Music Here Command

Moves the bot to your current voice channel.



#### Usage

	!movehere
	-  Moves the bot to your voice channel


<a name="MusicChannelCommand"></a>
### Music Channel Command

The music channel command can be used to define a text and voice channel that music should be linked to, if a text channel is set through the command, music commands will only work in the given channel, if a voice channel is set Ava will auto join the voice channel on the first music request.

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.


#### Usage

	!musicchannel
	-  Displays the current music channels.
	!musicchannel <voice|text>
	-  Disables the music text or voice channel.
	!musicchannel <voice|text> <channel>
	-  Sets the music text or voice channel.

#### Example

	!musicchannel text
	-  Disables the music text channel if one was set.
	!musicchannel voice music
	-  Sets the voice music channel to the `music` channel.

<a name="MusicMessagesCommand"></a>
### Music Messages Command

Toggles music messages on and off, when music messages are off, the "Now Playing" messages will no longer be sent, and messages that before would stay, will now be automatically be deleted after awhile. 

**Special permissions required to run this command**<br>The user needs **Administrator** permission to run this command.


#### Usage

	!musicmessages
	-  Displays the current music message status.
	!musicmessages [on|off]
	-  Toggles the music messages on/off.

#### Example

	!musicmessages off
	-  Turns off music messages.

<a name="PauseCommand"></a>
### Pause Music Command

Pauses the music currently playing


 - [Resume Music Command](#ResumeCommand)

#### Usage

	!pause
	-  Pauses the music


<a name="PlayCommand"></a>
### Play Music Command

Plays the provided song for you, if just the song title is given the bot will search YouTube for your song and give you some suggestions, you can also use YouTube, SoundCloud, TwitchTV, Bandcamp, and Vimeo link, or raw sound file, mp3, flac, wav, webm, mp4, ogg, aac, m3u and pls formats.


 - [SoundCloud Command](#SoundcloudCommand)

#### Usage

	!play <song>
	-  Plays the given song

#### Example

	!play A cool song
	-  Finds songs with the name "A cool song".
	!play https://www.youtube.com/watch?v=dQw4w9WgXcQ
	-  Plays the song off a link

<a name="PlaylistCommand"></a>
### Playlist Command

Music playlist command, allows music DJs to create, delete, and load playlists to the music queue, as well as adding and removing songs from any of the playlists.



#### Usage

	!playlist
	-  Lists existing playlists.
	!playlist [name] add [song link]
	-  Adds a song to a playlist.
	!playlist [name] create
	-  Creates a new playlist.
	!playlist [name] delete
	-  Deletes an existing playlist.
	!playlist [name] play
	-  Plays a playlist.
	!playlist [name] removesong [id]
	-  Removes a song from a playlist.
	!playlist [name] renameto [new name]
	-  Renames a existing playlist.
	!playlist [name] movesong [id] [new id]
	-  Move a song to a different position.
	!playlist [name] [page number]
	-  Shows the songs in a playlist.

#### Example

	!playlist test create
	-  Creates a playlist called `test`.
	!playlist test add Some song
	-  Adds `Some song` to the `test` playlist.
	!playlist test move 2 1
	-  Moves the 2nd song to the first place.
	!playlist test remove 2
	-  Removes the 2nd song from the `test`playlist.
	!playlist test rename Music
	-  Renames the `test` playlist to `Music`.
	!playlist music 2
	-  Shows the 2nd page of the `Music` playlist.
	!playlist music play
	-  Plays all the songs in the `Music` playlist.
	!playlist music delete
	-  Deletes the `Music` playlist.

<a name="RemoveSongFromQueueCommand"></a>
### Remove Song From Queue

Removes a song or multiple songs from the music queue.



#### Usage

	!removesong <song id> Removes the song with the given ID from the queue.
	!removesong <start song id> - <end song id> Removes the songs with the given range of IDs, inclusive, from the queue

#### Example

	!removesong 3 Removes song 3 from the queue
	!removesong 3-6 Removes songs 3-6 from the queue

<a name="RepeatMusicQueueCommand"></a>
### Repeat Music Command

Repeats all the songs in the music queue.



#### Usage

	!repeatsongs
	-  Toggles queue looping on or off.


<a name="ResumeCommand"></a>
### Resume Music Command

Resumes the music in the queue, starting the music back up if it was paused


 - [Pause Music Command](#PauseCommand)

#### Usage

	!resume
	-  Resumes the music


<a name="SeekCommand"></a>
### Seek Command

Jumps to the given time code in the track that is currently playing.



#### Usage

	!seek <time>
	-  Jumps to the given time code.

#### Example

	!seek 2:24
	-  Jumps to 2 minutes 24 seconds of the song.

<a name="SetDefaultVolumeCommand"></a>
### Set Default Volume Command

Sets the default volume that the music should play at when Ava first joins a voice channel.
**Note:** This does not change the volume of music already playing, to change that, use the `b!volume` command instead.



#### Usage

	!default-volume
	-  Displays the current default volume
	!default-volume <volume>
	-  Changes the default volume to the given volume.

#### Example

	!default-volume 75
	-  Sets the default volume to 75

<a name="ShuffleCommand"></a>
### Shuffle Command

Shuffles the music queue, mixing the songs up in random order.



#### Usage

	!shuffle
	-  Shuffles all the songs currently in the queue.


<a name="SkipCommand"></a>
### Skip Music Command

Skips to the next song in the music queue.


 - [Vote Skip Command](#VoteSkipCommand)

#### Usage

	!skip
	-  Skips to the next song in the queue


<a name="SongCommand"></a>
### Music Song Command

Returns the song that is playing right now and some attached information. This includes who requested it, how much of the song is left and the volume the song is playing at plus the rest of the songs currently in queue.



#### Usage

	!song
	-  Shows info about the song currently playing and the queue.
	!song [page]
	-  Shows the songs in the given page in the queue.


<a name="SoundcloudCommand"></a>
### SoundCloud Command

Plays the provided song for you, if just the song title is given the bot will search SoundCloud for your song and give you some suggestions, you can also use YouTube, SoundCloud, TwitchTV, Bandcamp, and Vimeo link, or raw sound file, mp3, flac, wav, webm, mp4, ogg, aac, m3u and pls formats.


 - [Play Music Command](#PlayCommand)

#### Usage

	!soundcloud <song>
	-  Plays the given song

#### Example

	!soundcloud A cool song
	-  Finds songs with the name "A cool song".
	!soundcloud https://soundcloud.com/yellowclaw/yellow-claw-flux-pavilion-catch-me-feat-naaz
	-  Plays the song off a link

<a name="StopCommand"></a>
### Stop Command

Stops the song currently playing, clears the music queue and disconnects from the voice channel the music was playing in.



#### Usage

	!stop
	-  Stops the music if anything is playing.


<a name="VoiceFixCommand"></a>
### Voice Fix Command

Music will sometimes stop working when Discord forgets to notify bots about voice state changes, this commands tries to make fixing that a bit easier to do by forcing a voice update state for the bot through changing the server region, the command will pick a server region at random, swap the servers region to that, and then 2½ seconds later swap right back, this should fix music 99% of the time.

 If you're still experiencing voice issues you can try making the bot leave the voice channel by using a command like `b!stop`, and then running this command again.

 Still having issues even after all that?
You can join the [support server](https://discord.gg/gt2FWER) to get help from the AvaIre support team directly.

**Special permissions required to run this command**<br>The bot needs **Manage Server** permission to run this command.


#### Usage

	!voicefix
	-  Finds a random server region, swaps to it and then swaps back again.


<a name="VolumeCommand"></a>
### Music Volume Command

Changes the volume of the music, by default the music will be playing at 100% volume.



#### Usage

	!volume
	-  Shows the current music volume without changing it
	!volume <volume>
	-  Sets the music volume to the given number

#### Example

	!volume 80

<a name="VoteSkipCommand"></a>
### Vote Skip Command

Use this command to vote on the song currently playing to be skipped, if the vote wins with a majority vote the song will be skipped.


 - [Skip Music Command](#SkipCommand)

#### Usage

	!voteskip
	-  Vote to skip the current song.



<a name="search"></a>
## Search

<a name="DuckDuckGoCommand"></a>
### DuckDuckGo Command

Searches [DuckDuckGo.com](https://duckduckgo.com/) with the given query and returns the first six results, if the command is used in a channel with NSFW disabled, all NSFW search results will be removed from the results.



#### Usage

	!duckduckgo <query>
	-  Searchs DuckDuckGo for your query.

#### Example

	!duckduckgo AvaIre Bot

<a name="GfycatCommand"></a>
### Gfycat Command

Returns a random gif for you from gfycat.com with the given query.



#### Usage

	!gfycat <query>
	-  Finds a random image with the given query

#### Example

	!gfycat cats

<a name="UrbanDictionaryCommand"></a>
### Urban Dictionary Command

Get the definition of a word or sentence from [urbandictionary.com](https://www.urbandictionary.com/).



#### Usage

	!urbandictionary <word or sentence>
	-  Gets the definition from Urban Dictionary

#### Example

	!urbandictionary potato

<a name="XKCDCommand"></a>
### XKCD Command

Gets the latest XKCD comic, or the comic with the given id.



#### Usage

	!xkcd
	-  Gets the latest comic
	!xkcd <id>
	-  Gets the comic with the given id.
	!xkcd random
	-  Gets a random comic.

#### Example

	!xkcd 530
	-  Gets the comic with an ID of `530`.
	!xkcd random
	-  Gets a random comic.


<a name="utility"></a>
## Utility

<a name="CalculateCommand"></a>
### Calculate Command

Calculates the given math equations and returns the result for you.



#### Usage

	!calculate <equation>
	-  Calculates the result of the given math equation.

#### Example

	!calculate (-50 + sqrt(50 ^ 2 - ((4 * 5) * (100 - 955)))) / (2 * 5) == 9

<a name="ChannelIdCommand"></a>
### Channel ID Command

Shows the ID of the channel the command was ran in, or the channel tagged in the command.


 - [Channel Info Command](#ChannelInfoCommand)

#### Usage

	!channelid [channel]
	-  Gets the ID of the current channel, or the mentioned channel.

#### Example

	!channelid #general
	!channelid

<a name="ChannelInfoCommand"></a>
### Channel Info Command

Shows information about the channel the command was run in, or the mentioned channel.


 - [Channel ID Command](#ChannelIdCommand)

#### Usage

	!channelinfo [channel]
	-  Gets information about the mentioned channel, or if no channel was mention, get information about the current channel.

#### Example

	!channelinfo #general
	!channelinfo

<a name="ExpandUrlCommand"></a>
### Expand Command

Expands the url to the full form, resolving all the redirects and showing what urls the link goes through if it redirects anywhere.



#### Usage

	!expand <url>
	-  Expands the provided url.

#### Example

	!expand https://avairebot.com/support

<a name="FeedbackCommand"></a>
### Feedback Command

Send feedback about Ava back to the developers and the staff team, any message passed to the command will be sent in the [#feedback](https://discord.gg/gt2FWER) channel on the [AvaIre Central](https://discord.gg/gt2FWER) server.



#### Usage

	!feedback <message>
	-  Sends feedback to the devs.

#### Example

	!feedback The thing about the stuff is doing stuff that doesn't make sense for the thing.

<a name="GlobalLeaderboardCommand"></a>
### Global Leaderboard Command

Shows the top 100 users globally, combining their rank, level, and xp between all servers the users are on.


 - [Rank Command](#RankCommand)
 - [Leaderboard Command](#LeaderboardCommand)

#### Usage

	!gleaderboard
	-  Displays the top 100 players on the XP leaderboard globally.

#### Example

	!gleaderboard 2

<a name="IPInfoCommand"></a>
### IP Info Command

Gives information about the given IP address.



#### Usage

	!ipinfo <ip>
	-  Displays information about the given IP address.

#### Example

	!ipinfo 8.8.4.4

<a name="InviteCommand"></a>
### Invite Command

Returns a link that can be used to invite the bot to other servers.



#### Usage

	!invite
	-  Gives you an invite link that can be used to invite AvaIre to servers.


<a name="LeaderboardCommand"></a>
### Leaderboard Command

Displays the server's level leaderboard with the user's name, rank, level and XP. The response is paginated to show 10 users per page.


 - [Rank Command](#RankCommand)
 - [Global Leaderboard Command](#GlobalLeaderboardCommand)

#### Usage

	!leaderboard
	-  Displays the top 100 players on the XP leaderboard for the server.

#### Example

	!leaderboard 2

<a name="PingCommand"></a>
### Ping Command

Can be used to check if the bot is still alive.



#### Usage

	!ping
	-  Returns the latency of the bot.


<a name="RankCommand"></a>
### Rank Command

Gets your rank, level, xp for the current server and total xp for all servers that you're on, you can tag a user to see their level stats instead.
This command requires the `Levels & Experience` feature to be enabled for the server!


 - [Leaderboard Command](#LeaderboardCommand)
 - [Global Leaderboard Command](#GlobalLeaderboardCommand)

#### Usage

	!rank
	-  Displays your rank, level, xp and other stuff
	!rank @Senither
	-  Displays Senither's rank, level, xp...

#### Example

	!rank @Senither

<a name="RemindCommand"></a>
### Remind Command

Reminds you of something after a certain amount of time.



#### Usage

	!remindme me <time> <message>
- Reminds you about the message after the time is up in a DM.
	!remindme here <time> <message>
- Reminds you about the message after the time is up in the channel the command was used in.

#### Example

	!remindme me 25m Something
	-  Reminds you about something after 25 minutes.
	!remindme me 2h30m9s Stuff
	-  Reminds you about stuff after 2 hours, 30 minutes, and 9 seconds.
	!remindme here 30m Potatoe
	-  Reminds you about Potatoe in 30 minutes in the current channel.

<a name="ServerIdCommand"></a>
### Server ID Command

Shows the ID of the server the command was ran in.


 - [Server Info Command](#ServerInfoCommand)



<a name="ServerInfoCommand"></a>
### Server Info Command

Shows information about the server the command was ran in.


 - [Server ID Command](#ServerIdCommand)



<a name="ShardCommand"></a>
### Shard Command

Displays the status of all the shards for the bot, including their server count, channel count, user count and latency.



#### Usage

	!shards [page] Displays the shard information, with 12 shards per page.

#### Example

	!shards 2
	-  Displays the 2nd page of shard information.

<a name="SourceCommand"></a>
### Source Command

Gives you the source code for the Bot, or the code for a given command.



#### Usage

	!source
	-  Returns the full source code for the bot.
	!source <command>
	-  Returns the source code for the given command.

#### Example

	!source ping

<a name="StatsCommand"></a>
### Stats Command

Displays information about Ava and some related stats.



#### Usage

	!stats
	-  Shows some stats about the bot.


<a name="UptimeCommand"></a>
### Uptime Command

Displays how long the bot has been online for.



#### Usage

	!uptime
	-  Displays how long the bot has been online for.


<a name="UserAvatarCommand"></a>
### User Avatar Command

Get the profile picture of someone on the server by name, id, or mentions.



#### Usage

	!avatar <user | user id>
	-  Gets the avatar of the given user.

#### Example

	!avatar @Senither
	!avatar

<a name="UserIdCommand"></a>
### User ID Command

Shows your Discord account user ID, or the ID of the user tagged in the command.


 - [User Info Command](#UserInfoCommand)

#### Usage

	!userid [user]
	-  Gets the ID of the user who ran the command, or the mentioned user.

#### Example

	!userid @Senither
	!userid alexis
	!userid 88739639380172800

<a name="UserInfoCommand"></a>
### User Info Command

Shows information about the user that ran the command, or the mentioned user. This includes the users username, ID, roles, the date they joined the server, the date they created their account, and how many servers they're in (That Ava knows about).


 - [User ID Command](#UserIdCommand)

#### Usage

	!userinfo [user]
	-  Gets information about the user who ran the command, or the mentioned user

#### Example

	!userinfo @Senither
	!userinfo alexis
	!userinfo 88739639380172800

<a name="VersionCommand"></a>
### Version Command

Displays the current version of Ava that is running. If the version is outdated the new version will be shown as well as what type of changes have been made.




#### Example

	!version
	-  Gets the current version of the bot, and displays any changes compared to the master branch if there is any.

<a name="VoteCommand"></a>
### Vote Command

Enjoy using the bot? Consider voting for the bot to help it grow, it's free but means a lot to the team behind Ava <3



#### Usage

	!vote check
	-  Checks if you have voted for Ava in the last 12 hours.
	!vote
	-  Displays the invite link to Ava, or tells you when your vote expires.

#### Example

	!vote check

