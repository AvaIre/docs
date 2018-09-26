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

<a name="AiCommand"></a>
### AI

Toggles the AI module on or off for the current channel. If the module is enabled, users can tag the bot followed by a message or question and the bot will try and use its AI to process the message. By default AI messages will be enabled for all channels.

The **Manage Server** permission is required to run this command.

#### Usage

    !ai - Toggles the AI ON or OFF for the current channel.

<a name="ListAliasesCommand"></a>
### Alias

Creates and maps a custom aliases for a pre-existing command. If an alias that already exists is given with no additional command the alias will be unbound.

The **Manage Server** permission is required to run this command.

#### Usage

    !alias <alias> - Deletes the alias if it exists.
    !alias <alias> <command> - Creates an alias for the given command.

#### Aliases

    !cmdmap

<a name="AliasesCommand"></a>
### Aliases

Lists all the existing command aliases and what they're bound to.

The **Manage Server** permission is required to run this command.

#### Usage

    !aliases [page]

#### Aliases

    !aliaslist

<a name="AddLevelRoleCommand"></a>
### Add Level Role

Adds a role to the leveling up table, roles on the table will be given to users once they level up and meet the requirements for the role.

 - [List Level Roles](#ListLevelRolesCommand)
 - [Remove Level Role](#RemoveLevelRoleCommand)

The **Server Administrator** permission is required to run this command.

#### Usage

    !alr <level requirement> <role> - Adds to role to users when they level up and meet the level requirement.

<a name="AddSelfAssignableRoleCommand"></a>
### Add Self Assignable Role

Adds a role to the self-assignable roles list, any role on the list can be claimed by users when they use [!iam](#IAmCommand) or unclaimed with [!iamnot](#IAmNotCommand).

 - [List Self Assignable Roles](#ListSelfAssignableRolesCommand)
 - [Remove Self Assignable Role](#RemoveSelfAssignableRoleCommand)

The **Server Administrator** permission is required to run this command.

#### Usage

    !asar <role> - Adds the mentioned role to the self-assignable roles list.

<a name="AutoAssignRoleCommand"></a>
### Auto Assign Role

Automatically assigns a specified role to every user who joins the server, if no arguments is given the current auto assignable role will be given, if a name is given the role will be set as the auto assignable role, and if disabled is given the feature will be turned off.

The **Server Administrator** permission is required to run this command.

#### Usage

    !autorole - Displays the current auto assignable role if one is set.
    !autorole <role> - The role that should be auto assignable.
    !autorole disable - Disables the auto assignable role.

#### Aliases

    !aar

<a name="UserAvatarCommand"></a>
### Avatar

Get the profile picture of someone on the server by name, id, or mentions.

#### Usage

    !avatar <user | user id> - Gets the avatar of the given user.

<a name="BanCommand"></a>
### Ban

Bans the mentioned user from the server with the provided reason, all messages the user has sent in the last 7 days will also be deleted in the process.

The **Ban Members** permission is required to run this command.

> This action will be reported to any channel that has [modlogging](#modlog) enabled on the server.

#### Usage

    !ban <user> [reason]

<a name="CategoriesCommand"></a>
### Categories

Shows status of all command categories in the current or mentioned channel, both for globally and per-channel. You can tag a channel if you want to see the command category status for the given channel.

#### Usage

    !categories [channel] - Displays the status of the command categories in the mentioned channel, or the current channel if no channel was mentioned.

#### Aliases

    !cats

<a name="ChangePrefixCommand"></a>
### Change Prefix

Sets the prefix that should be used for all commands in a given category, if no prefix is provided the category prefix will be reset back to the default instead.

> {tip} Command prefixes cannot contain spaces.

The following categories can be affected by this command.

 - [Administration](#administration)
 - [Fun](#fun)
 - [Help](#help)
 - [Music](#music)
 - [Search](#search)
 - [Utility](#utility)

The **Server Administrator** permission is required to run this command.

> {tip} It is not required to type out the full name of the category, just typing a few characters will get the category that starts with the given characters.<br>For example changing the prefix all the commands in the `Administration` category can be done by doing `!changeprefix a [prefix]` for short.

#### Usage

    !changeprefix <category> - Resets the category prefix back to its default prefix.
    !changeprefix <category> [prefix] - Sets the category prefix to the given prefix.

#### Aliases

    !prefix

<a name="DJLevelCommand"></a>
### DJ Level

Change the DJ level requirement for the server, this changes what music commands people can use with or without the DJ Discord role.

#### Usage

    !djlevel - Displays the current DJ Level for the server.
    !djlevel types - Displays all the types and some info about them.
    !djlevel <type> - Change the DJ Level to the given type.

<a name="GoodbyeCommand"></a>
### Goodbye

Toggles the goodbye module on or off for the current channel. When the goodbye module is enabled, a message will be sent in the channel every time someone leaves the server.

The **Manage Server** permission is required to run this command.

#### Usage

    !goodbye

#### Aliases

    !bye

<a name="GoodbyeMessageCommand"></a>
### Goodbye Message

Sets the message that should be sent when a user leaves the server, this command can only be used if the goodbye module is enabled for the current channel. You can customize how the goodbye message looks using [placeholders](/docs/{{version}}/placeholders).

The **Manage Server** permission is required to run this command.

#### Usage

    !goodbyemessage - Resets the goodbye back to the default message.
    !goodbyemessage <message> - Sets the goodbye message to the given message.
    !goodbyemessage <user> - If a valid username, nickname or user was mentioned, an example message will be sent for the given user.

#### Aliases

    !byemsg

<a name="IAmCommand"></a>
### I Am

Gives you the role with the given name if it is in the self-assignable list of roles.

#### Usage

    !iam <role>

<a name="IAmNotCommand"></a>
### I Am Not

Removes the role with the given name from you if it is in the self-assignable list of roles.

#### Usage

    !iamnot <role>

#### Aliases

    !iamn

<a name="KickCommand"></a>
### Kick

Kicks the mentioned user from the server with the provided reason, this action will be reported to any channel that has modloging enabled.

The **Kick Members** permission is required to run this command.

> This action will be reported to any channel that has [modlogging](#modlog) enabled on the server.

#### Usage

    !kick <user> [reason] - Kicks the mentioned user with the given reason.

<a name="LanguageCommand"></a>
### Language

Show a list of available languages or set a language that should be used for the server.

The **Server Administrator** permission is required to run this command.

#### Usage

    !language [page] - Displays a list of languages, 10 languages per page.
    !language [code] - Sets the language to the given language code.

<a name="LevelAlertsCommand"></a>
### Level Alerts

Toggles the Leveling alerts system on or off for the current server or channel. When the level alerts are enabled the bot will send a message each time a user levels up, letting them know they leveled up and what level they are now.

The **Manage Server** permission is required to run this command.

#### Usage

    !levelalerts - Toggles the level alerts feature on/off
    !levelalerts <channel> - Toggles the level alerts feature on for the given channel

#### Aliases

    !lvlalert

<a name="ListLevelRolesCommand"></a>
### List Level Roles

List all the leveling roles and the level require to get them.

 - [Add Level Role](#AddLevelRoleCommand)
 - [Remove Level Role](#RemoveLevelRoleCommand)

#### Usage

    !llr - Lists all the roles you can get for leveling up.

<a name="ListSelfAssignableRolesCommand"></a>
### List Self Assignable Roles

List all the self-assignable roles, 10 per-page.

 - [Add Self Assignable Role](#AddSelfAssignableRoleCommand)
 - [Remove Self Assignable Role](#RemoveSelfAssignableRoleCommand)

#### Usage

    !lsar

<a name="NSFWCommand"></a>
### NSFW

Displays the NSFW status of the current channel, additionally on/off can be passed to the command to change the channels NSFW status.

The **Manage Channels** permission is required to run this command.

#### Usage

    !nsfw - Displays the NSFW status of the current channel.
    !nsfw <on | off> - Changes the NSFW status of the current channel.
    !nsfw <channel> - Displays the mentioned channels NSFW status
    !nsfw <channel> <on | off> - Changes the NSFW status of the mentioned channel.

<a name="ModlogCommand"></a>
### Modlog

Displays the modlogging status for the server if no arguments is given, you can also mention a text channel to enable modlogging and set it to the mentioned channel.

The **Manage Server** permission is required to run this command.

#### Usage

    !modlog - Displays the current state of the modlog module for the server.
    !modlog <channel> - Enabled modlogging and sets it to the mentioned channel.
    !modlog disable - Disables the modlogging module for the server.

<a name="ModlogHistoryCommand"></a>
### Modlog History

Displays the modlog history for the mentioned user, this will display all past warnings, bans, soft bans, kicks, and voice kicks.

The **Manage Server** permission is required to run this command.

#### Usage

    !modloghistory <user> - Displays the modlog history for the mentioned user.

#### Aliases

    !history

<a name="PurgeCommand"></a>
### Purge

Deletes up to 100 chat messages in any channel, you can mention a user if you only want to delete messages by the mentioned user. Due to a restriction in the Discord API, the purge command will only work on messages sent in the last 14 days.

The **Manage Messages** permission is required to run this command.

> {tip} Tagging a user will only delete any messages they have sent in the last `<amount>` of messages, for example `!purge 100 @JohnDoe#2854` will delete any messages the JohnDoe user has sent within the last 100 messages.

#### Usage

    !purge - Deletes the last 5 messages.
    !purge [number] - Deletes the given number of messages.
    !purge [number] [user] - Deletes the given number of messages for the mentioned users.

#### Aliases

    !clear

<a name="ModlogReasonCommand"></a>
### Modlog Reason

Sets the reason for an old modlog case, this command requires the server has a modlog channel set using the !modlog command.
You can only set modlog reasons for old modlog cases if you were the moderator for the case.

> {tip} You can only set modlog reasons for old modlog cases if you were the moderator for the case.

#### Usage

    !reason <case id> <reason> - Sets the reason for the given ID

<a name="RemoveLevelRoleCommand"></a>
### Remove Level Role

Remove a role from the leveling up role table.

 - [Add Level Role](#AddLevelRoleCommand)
 - [List Level Role](#ListLevelRolesCommand)

The **Server Administrator** permission is required to run this command.

#### Usage

    !rlr <role / level> - Removes the role from the leveling up role table.

<a name="RemoveSelfAssignableRoleCommand"></a>
### Remove Self Assignable Role

Removes the role from the self-assignable/claimable roles list, any role on the list can be claimed by users when they use [.iam](#IAmCommand) or unclaimed with [.iamnot](#IAmNotCommand).

 - [Add Self Assignable Role](#AddSelfAssignableRoleCommand)
 - [List Self Assignable Role](#ListSelfAssignableRolesCommand)

The **Server Administrator** permission is required to run this command.

#### Usage

    !rsar <role> - Removes the mentioned role from the self-assignable roles list.

<a name="SlowmodeCommand"></a>
### Slowmode

Disables the slowmode module or enables it with the given settings, users with the **Manage Messages** permission are exempt from slowmode limits. The slowmode module can be disabled by running the command with no arguments; if the `limit` and `decay` arguments are given the module will be enabled with the given settings.

The **Manage Server** permission is required to run this command.

#### Usage

    !slowmode <off> - Disables slowmode for the current channel.
    !slowmode <limit> <decay> - Enables slowmode with the given settings.

<a name="SoftBanCommand"></a>
### Softban

Bans the mentioned user from the server with the provided reason. Any messages the user might've sent won't be deleted, if you want to force delete any old messages the user has sent see the [ban command](#ban).

The **Ban Members** permission is required to run this command.

> This action will be reported to any channel that has [modlogging](#modlog) enabled on the server.

#### Usage

    !softban <user> [reason] - Bans the mentioned user with the given reason.

#### Aliases

    !sban

<a name="ToggleCategoryCommand"></a>
### Toggle Category

Toggles the given command category on or off for the given channel, optionally for the whole server. When a command category is disabled no one can run any commands in the command module, you can disable commands on a per-channel basis by tagging the channel you want to affect.

The **Server Administrator** permission is required to run this command.

> {tip} If you want to affect the whole server, you can completely omit the channel argument and just pass [on|off].

#### Usage

    !togglecategory <category> <global> [status] - Changes the command category status for the whole server.
    !togglecategory <category> <channel> [status] - Changes the command category status for the mentioned channel.

#### Aliases

    !tcategory
    !tcat

<a name="LevelCommand"></a>
### Toggle Level

Toggles the leveling system on or off for the current server. When the leveling system is enabled users will slowly accumulate XP from being active in the chat and using commands, every minute the user is active they will receive 10-15 XP.

The **Manage Server** permission is required to run this command.

#### Usage

    !togglelevel - Toggles the level feature on/off

#### Aliases

    !tlvl

<a name="VoiceKickCommand"></a>
### Voice Kick

Kicks the mentioned user from the voice channel they're currently connected to, 

The **Kick Members** permission is required to run this command.

> This action will be reported to any channel that has [modlogging](#modlog) enabled on the server.

#### Usage

    !voicekick <user> [reason] - Kicks the mentioned user with the given reason.

#### Aliases

    !vkick

<a name="WarnCommand"></a>
### Warn

Warns a given user with a message, this action will be reported to any channel that has modloging enabled.

The **Manage Messages** permission is required to run this command.

#### Usage

    !warn <user> [reason] - Warns the mentioned user with the given reason.

<a name="WelcomeCommand"></a>
### Welcome

Toggles the welcome module on or off for the current channel. When the welcome module is enabled, a message will be sent in the channel every time someone joins the server.

The **Manage Server** permission is required to run this command.

#### Usage

    !welcome

#### Aliases

    !wel

<a name="WelcomeMessageCommand"></a>
### Welcome Message

Sets the welcome message to the given message. If no arguments are passed the welcome message will be set back to the default welcome message. You can customize how the welcome message looks using [placeholders](/docs/{{version}}/placeholders).

The **Manage Server** permission is required to run this command.

#### Usage

    !welcomemessage - Resets the welcome back to the default message.
    !welcomemessage <message> - Sets the welcome message to the given message.
    !welcomemessage <user> - If a valid username, nickname or user was mentioned, an example message will be sent for the given user.

#### Aliases

    !welmsg

<a name="fun"></a>
## Fun Commands

<a name="EightBallCommand"></a>
### 8 Ball

Ask 8Ball a question and get a random response back.

#### Usage

    !8ball [message]

<a name="ChuckNorrisCommand"></a>
### Chuck Norris

Gets a random 100% true, real fact about Chuck Norris using the "Internet Chuck Norris Database".

#### Usage

    !chucknorris - Gets a random fact for you about "Chuck Norris".
    !chucknorris [name] - Gets a random fact for you, and changes the name "Chuck Norris" with the given name.

#### Aliases

    !chuck
    !norris

<a name="CoinflipCommand"></a>
### Coin Flip

Flips a coin for heads or tails.

#### Usage

    !coinflip

#### Aliases

    !coin

<a name="DiceCommand"></a>
### Dice

Rolls a set of dice with the given number of sides, for example using `4d8` will roll four eight sided dice.

#### Usage

    !dice <dice followed by a D and the sides> - Rolls some dice randomly.

<a name="FlipTextCommand"></a>
### Flip Message

Flips the given message upside down.

#### Usage

    !flip <message> - Flips the given message.

<a name="LennyCommand"></a>
### Lenny

( ͡° ͜ʖ ͡°)

#### Usage

    !lenny

<a name="MemeCommand"></a>
### Meme

Creates a meme of the given type. Passing list as an argument sends a full list of memes that can be generated via the bot. You can also tag a user to use that user's avatar as a meme instead.

#### Usage

    !meme list - Lists all the available meme types.
    !meme <meme> <top text> <bottom text> - Generates the meme with the given text.
    !meme <user> <top text> <bottom text> - Generates a meme with the mentioned users avatar and the given text.

#### Example

    !meme buzz "Memes" "Memes everywhere"
    !meme @Senither "Creates a Meme command for AvaIre" "Almost no one uses it"

<a name="RandomCatCommand"></a>
### Random Cat

Gets a random cat image from the internet.

#### Usage

    !randomcat

#### Aliases

    !cat

<a name="RandomDogCommand"></a>
### Random Dog

Gets a random dog image from the internet.

#### Usage

    !randomdog

#### Aliases

    !dog

<a name="RepeatCommand"></a>
### Repeat Message

Makes Ava repeat whatever you say.

#### Usage

    !repeat <message> - Repeats the given message

#### Aliases

    !echo

<a name="ReverseCommand"></a>
### Reverse Message

Reverses the message given.

#### Usage

    !reverse <message> - Reverses the given message.

<a name="RipCommand"></a>
### RIP

Pay your respects.

#### Usage

    !rip

<a name="RollCommand"></a>
### Roll

Roll a random number between 1 and 100, or within the given parameters.

#### Usage

    !roll [min] [max]

<a name="SayCommand"></a>
### Say

Makes Ava say whatever you want. If Ava has permissions to delete messages, the original message will be deleted and Ava's message will replace it.

#### Usage

    !say [message]

<a name="interaction"></a>
## Interaction Commands

Interaction commands are commands that will send a random gif matching the type of interaction command used.

All interaction commands requires a user to be mentioned in the command as the only argument, either by tagging the user, using the users ID, nickname or username, because all the interaction commands follows the same format, all the commands have been bundled up in a table for easier overview.

#### Example

If the command were to be used on a user called JohnDoe#1234 with a nickname of Johnny, all the following examples would be a valid use of a interaction command.

    !command @JhonDoe
    !command JhonDoe
    !command JhonDoe#1234
    !command Johnny
    !command 123321123321123321 <- This is Johns user ID

<a name="interaction-commands"></a>
### Commands

| Command           |  Description      |
| ----------------- |:---------------------- |
| !bite  | Bites the mentioned user.  |
| !cuddle  | Cuddles with the mentioned user.  |
| !divorce  | Divorces the mentioned user.  |
| !eats  | Eats some food with the mentioned user.  |
| !hello  | Waves hello to the mentioned user.  |
| !highfive  | Highfives the mentioned user.  |
| !hug  | Hugs the mentioned user.  |
| !kill  | Kills the mentioned user.  |
| !kiss  | Kisses the mentioned user.  |
| !pan  | Hits the mentioned user with a pan.  |
| !pat  | Pats the mentioned users head.  |
| !poke  | Pokes the mentioned user.  |
| !pouts  | Pouts at the mentioned user.  |
| !punch  | Punches the mentioned user.  |
| !senpai  | Sends a **notice me** image to the mentioned user.  |
| !shrugs  | Shrugs at the mentioned user.  |
| !slap  | Slaps the mentioned user.  |
| !tickle  | Tickles the mentioned user.  |
| !triggered  | Sends a **triggered** image to the mentioned user.  |

<a name="music"></a>
## Music Commands

<a name="ClearQueueCommand"></a>
### Clear Queue

Clears the music queue of all pending songs, removing all pending songs.

The **DJ** role is required to run this command.

#### Usage

    !clearqueue - Clears the music queue

#### Aliases

    !flushqueue
    !cqueue

<a name="SetDefaultVolumeCommand"></a>
### Set Default Volume Command

Sets the default volume that the music should play at when Ava first joins a voice channel.

> Note: This does not change the volume of music already playing, to change that, use the [!volume](#VolumeCommand) command instead.

The **DJ** role is required to run this command.

#### Usage

    !default-volume [volume]

#### Aliases

    !set-volume

<a name="MoveHereCommand"></a>
### Move Here

Moves the bot into the same voice channel you're in. This command can be used to move the bot to a different voice channel while it's playing music without having the permissions to move other users. 

The **DJ** role is required to run this command.

#### Usage

    !movehere

#### Aliases

    !moveh

<a name="MusicChannelCommand"></a>
### Music Channel

The music channel command can be used to define a text and voice channel that music should be linked to, if a text channel is set through the command, music commands will only work in the given channel, if a voice channel is set Ava will auto join the voice channel on the first music request.

The **Administrator** permission is required to run this command.

#### Usage

    !musicchannel - Displays the current music channels.
    !musicchannel <voice|text> - Disables the music text or voice channel.
    !musicchannel <voice|text> <channel> - Sets the music text or voice channel.

#### Aliases

    !mchannel

<a name="MusicMessagesCommand"></a>
### Music Channel

Toggles music messages on and off, when music messages are off, the "Now Playing" messages will no longer be sent, and messages that before would stay, will now be automatically be deleted after awhile. 

The **Administrator** permission is required to run this command.

#### Usage

    !musicmessages - Displays the current music message status.
    !musicmessages [on|off] - Toggles the music messages on/off.

#### Aliases

    !musicmessage

<a name="PauseCommand"></a>
### Pause

Pauses the song that is currently playing.

The **DJ** role is required to run this command.

#### Usage

    !pause

<a name="PlayCommand"></a>
### Play

Plays the provided song for you, if just the song title is given the bot will search YouTube for your song and give you some suggestions, you can also use YouTube, SoundCloud, TwitchTV, Bandcamp, and Vimeo link, or raw sound file, mp3, flac, wav, webm, mp4, ogg, aac, m3u and pls formats.

#### Usage

    !play <song> - Plays the given song

#### Aliases

    !request

#### Tag Example

    @AvaIre play <name of song>
    @AvaIre can you find me some chill music?

<a name="PlaylistCommand"></a>
### Playlist

Allows music DJs to create, list, update, and delete music playlists. This command has a bunch of sub-commands that are used to manage the playlists; to make it a bit easier, here are all the sub-commands.

 - [Add song to Playlist](#playlist-add)
 - [Create new Playlist](#playlist-create)
 - [Delete existing Playlist](#playlist-delete)
 - [Remove a song from an existing Playlist](#playlist-remove)
 - [Load Playlist into the Music queue](#playlist-load)
 - [List Songs in the Playlist](#playlist-list)
 - [Rename Playlist](#playlist-rename)

The **DJ** role is required to run this command.

#### Usage

    !playlist [name] [arguments]

#### Aliases

    !list
    !pl

<a name="playlist-add"></a>
### Playlist - Add a song to a playlist

Adds a song to the a existing playlist, if you don't already have playlist you can [create a new playlist](#playlist-create).

#### Usage

    !playlist <name> add <song url>

#### Aliases

    !playlist <name> a <song url>

**You can replace the `!playlist` command with any of [playlist command aliases](#playlist).**

<a name="playlist-create"></a>
### Playlist - Create new playlist

Creates a new playlist for the server with the given name. When the playlist has been created you can start [adding songs to it](#playlist-add), if you butchered the name you can [rename the playlist](#playlist-rename) without deleting all the songs in it.

#### Usage

    !playlist <name> create

#### Aliases

    !playlist <name> c

**You can replace the `!playlist` command with any of [playlist command aliases](#playlist).**

<a name="playlist-delete"></a>
### Playlist - Delete a playlist

Deletes a playlist and all the songs in it. **Keep in mind that deleting the playlist is a permanent action and can not be undone!** There is **NO** confirmation if you are sure that you want to delete it; the playlist will just be deleted if you use the command.

> {tip} If the playlist is loaded into the music queue when the playlist is deleted, the music will still continue to play all the way through.

#### Usage

    !playlist <name> delete

**You can replace the `!playlist` command with any of [playlist command aliases](#playlist).**

<a name="playlist-remove"></a>
### Playlist - Remove a song from an existing playlist 

Removes the song with the given ID for the current playlist if it's in queue.

#### Usage

    !playlist <name> removesong <ID>

#### Aliases

    !playlist <name> remove <ID>

**You can replace the `!playlist` command with any of [playlist command aliases](#playlist).**

<a name="playlist-load"></a>
### Playlist - Load a playlist into the queue

Loads the playlist into the music queue. If the bot is not already playing music this command will also connect the bot to the same voice channel you are in and initialize music playback. If the playlist is empty you can [add some songs](#playlist-add).

#### Usage

    !playlist <name> load

#### Aliases

    !playlist <name> play
    !playlist <name> l

**You can replace the `!playlist` command with any of [playlist command aliases](#playlist).**

<a name="playlist-list"></a>
### Playlist - List songs in the playlist

Lists the songs in the playlist with the given name. The response will be paginated to only show ten songs at a time; you can jump to different pages by passing a page number for the playlist as an additional argument. If you don't have any songs in the playlist you can [add songs](#playlist-add).

#### Usage

    !playlist <name> [page number]

**You can replace the `!playlist` command with any of [playlist command aliases](#playlist).**

<a name="playlist-rename"></a>
### Playlist - Rename a playlist

Rename an existing playlist. The string passed to the command will be used as the new name.

#### Usage

    !playlist <name> renameto <new name>

#### Aliases

    !playlist <name> rename <new name>
    !playlist <name> r <new name>

**You can replace the `!playlist` command with any of [playlist command aliases](#playlist).**

<a name="RemoveSongFromQueueCommand"></a>
### Remove Song from Queue

Removes the song with the given ID from the queue, you can get the song ID in the queue by using the [!](!queue) command.

#### Usage

    !removesong <song id> Removes the song with the given ID from the queue.

#### Aliases

    !songremove

<a name="RepeatMusicQueueCommand"></a>
### Repeat Music Queue

Toggles music looping on or off, the [queue](#queue) command be used to get the music looping status.

The **DJ** role is required to run this command.

#### Usage

    !repeatsongs

#### Aliases

    !repeatqueue
    !loop

<a name="ResumeCommand"></a>
### Resume

Resumes the music in the queue, starting the music back up if it was paused.

The **DJ** role is required to run this command.

#### Usage

    !resume

<a name="SeekCommand"></a>
### Seek

Jumps to the given time in the song currently playing.

The **DJ** role is required to run this command.

#### Usage

    !seek <time> - Jumps to the given time.

#### Aliases

    !goto

<a name="ShuffleCommand"></a>
### Shuffle

Shuffles the music queue, mixing the songs up in random order.

The **DJ** role is required to run this command.

#### Usage

    !shuffle

<a name="SkipCommand"></a>
### Skip

Skips to the next song in the music queue.

The **DJ** role is required to run this command.

#### Usage

    !skip

<a name="SongCommand"></a>
### Song Command

Returns the song that is playing right now and some attached information. This includes who requested it, how much of the song is left and the volume the song is playing at plus the rest of the songs currently in queue. 

#### Usage

    !song - Shows info about the song currently playing and the queue.
    !song [page] - Shows the songs in the given page in the queue.

#### Aliases

    !songs
    !queue

<a name="SoundcloudCommand"></a>
### Soundcloud

Plays the provided song for you, if just the song title is given the bot will search SoundCloud for your song and give you some suggestions, you can also use YouTube, SoundCloud, TwitchTV, Bandcamp, and Vimeo link, or raw sound file, mp3, flac, wav, webm, mp4, ogg, aac, m3u and pls formats.

#### Usage

    !soundcloud <song> - Plays the given song

#### Aliases

    !sc

#### Tag Example

    @AvaIre sc <name of song>

<a name="StopCommand"></a>
### Stop

Stops the song currently playing, clears the music queue and disconnects from the voice channel the music was playing in.

The **DJ** role is required to run this command.

#### Usage

    !stop

<a name="VolumeCommand"></a>
### Volume

Changes the volume of the music, by default the music will be playing at 50% volume.

The **DJ** role is required to run this command.

#### Usage

    !volume - Shows the current music volume without changing it.
    !volume <volume> - Sets the music volume to the given number.

#### Aliases

    !vol

<a name="VoteSkipCommand"></a>
### Vote Skip

Use this command to vote on the song currently playing to be skipped, if the vote wins with a majority vote the song will be skipped.

#### Usage

    !voteskip

#### Aliases

    !vskip

<a name="search"></a>
## Search Commands

<a name="DuckDuckGoCommand"></a>
### Search

Searches DuckDuckGo.com with the given query and returns the first six results, if the command is used in a channel with NSFW disabled, all NSFW search results will be removed from the results.

#### Usage

    !duckduckgo <query>

#### Aliases

    !ddg
    !g

<a name="GfycatCommand"></a>
### Gfycat

Gets a random gif from [gfycat.com](https://gfycat.com/) with the given query.

#### Usage

    !gfycat <query>

#### Aliases

    !gif

<a name="UrbanDictionaryCommand"></a>
### Urban Dictionary

Get the definition of a word or sentence from [urbandictionary.com](http://www.urbandictionary.com/).

#### Usage

    !urbandictionary [word or sentence]

#### Aliases

    !urban

<a name="XKCDCommand"></a>
### XKCD

Gets the latest [xkcd](https://xkcd.com/) comic, or the comic with the given ID.

#### Usage

    !xkcd [comic ID]

<a name="utility"></a>
## Utility Commands

<a name="CalculateCommand"></a>
### Calculate

Calculates the given math equations and returns the result for you.

#### Usage

    !calculate <equation> - Calculates the result of the given math equation.

#### Aliases

    !calc

<a name="ChannelIdCommand"></a>
### Channel ID

Shows the ID of the channel the command was ran in, or the channel tagged in the command.

#### Usage

    !channelid [channel]

#### Aliases

    !cid

<a name="ChannelInfoCommand"></a>
### Channel Info

Shows information about the channel the command was run in, or the mentioned channel.

#### Usage

    !channelinfo [channel]

#### Aliases

    !cinfo

<a name="ExpandUrlCommand"></a>
### Expand URL

Expands the url to the full form, resolving all the redirects and showing what urls the link goes through if it redirects anywhere.

#### Usage

    !expand <url> - Expands the provided url.

#### Aliases

    !resolve
    !e

<a name="FeedbackCommand"></a>
### Feedback

Send feedback about Ava back to the developers and the staff team, any message passed to the command will be sent in the [#feedback](https://discord.gg/gt2FWER) channel on the [AvaIre Central](https://discord.gg/gt2FWER) server.

#### Usage

    !feedback <message>

<a name="GlobalLeaderboardCommand"></a>
### Global Leaderboard

Shows the top 100 users globally, combining their rank, level, and xp between all servers the users are on. The response is paginated to show 10 users per page.

#### Usage

    !gleaderboard [page]

#### Aliases

    !gtop

<a name="InviteCommand"></a>
### Invite

Returns a link that can be used to invite the bot to other servers.

#### Usage

    !invite - Gives you an invite link that can be used to invite AvaIre to servers.

#### Aliases

    !join

<a name="IPInfoCommand"></a>
### IP Info

Gives information about the given IP address.

#### Usage

    !ipinfo <ip> - Displays information about the given IP address.

<a name="LeaderboardCommand"></a>
### Leaderboard

Displays the server's level leaderboard with the user's name, rank, level and XP. The response is paginated to show 10 users per page.

The **[Levels & Experience](#level)** feature must be enabled to run this command.

#### Usage

    !leaderboard [page]

#### Aliases

    !top

<a name="PingCommand"></a>
### Ping

Can be used to check if the bot is still alive.

#### Usage

    !ping - Returns the latency of the bot.

<a name="RankCommand"></a>
### Rank

This command requires the Levels & Experience feature to be enabled for the server!
Displays the user's rank, level, XP and how much XP they need to level up, as well as their total xp between all servers they're on.

The **[Levels & Experience](#level)** feature must be enabled to run this command.

#### Usage

    !rank - Displays your rank, level, xp and other stuff
    !rank @Senither - Displays Senither's rank, level, xp...

#### Aliases

    !level

<a name="RemindCommand"></a>
### Remind Me

Reminds you of something after a certain amount of time.

#### Usage

    !remindme me <time> <message> - Reminds you about the message after the time is up in a DM.
    !remindme here <time> <message> - Reminds you about the message after the time is up in the channel the command was used in.

#### Aliases

    !remind

<a name="ServerIdCommand"></a>
### Server ID

Displays ID of the server the command was ran in.

#### Usage

    !serverid

#### Aliases

    !sid

<a name="ServerInfoCommand"></a>
### Server Info

Displays information about the server the command was ran in. This includes the server's ID, owner, text and voice channels, members, roles, region, avatar and when it was created.

#### Usage

    !serverinfo

#### Aliases

    !sinfo

<a name="ShardCommand"></a>
### Shards

Displays the status of all the shards for the bot, including how many servers, channels and users each shard is connected to.

> If the bot instance is not started in a sharded state the [!stats](#StatsCommand) command will be used instead.

#### Usage

    !shards

#### Aliases

    !shard

<a name="SourceCommand"></a>
### Source

Gives you the source code for the Bot, or the code for a given command.

#### Usage

    !source - Returns the full source code for the bot.
    !source <command> - Returns the source code for the given command.

<a name="StatsCommand"></a>
### Stats

Displays information about Ava and some related stats. The following information will be returned.

 - Bot ID
 - Author of the bot
 - The current version of the bot
 - The last few changes to the latest version of Ava
 - Library the bot is written in
 - How many database queries have been run
 - How many messages have been received
 - How many servers Ava is playing music in right now
 - How many servers Ava is in
 - How many commands have been run
 - How much memory Ava is using
 - How many users Ava knows about (total, total online, unique and unique online)
 - How many channels Ava knows about (total, text and voice)
 - How long Ava has been online

#### Usage

    !stats - Shows some stats about the bot.

#### Aliases

    !about

<a name="UptimeCommand"></a>
### Uptime

Displays how long the bot has been online for.

#### Usage

    !uptime

<a name="UserIdCommand"></a>
### User ID

Displays ID of the user who ran the command or the ID of the mentioned user.

#### Usage

    !userid [user]

#### Aliases

    !uid

<a name="UserInfoCommand"></a>
### User Info

Displays information about the user who ran the command or the mentioned user. This includes the users username, ID, roles, the date they joined the server, the date they created their account, and how many servers they're in (That Ava knows about).

#### Usage

    !userinfo [user]

#### Aliases

    !uinfo

<a name="VersionCommand"></a>
### Version

Displays the current version of Ava you're running. If the version is outdated the new version will be shown as well as what type of changes have been made.

#### Usage

    !version

<a name="VoteCommand"></a>
### Vote

Enjoy using the bot? Consider voting for the bot to help it grow, it's free but means a lot to the team behind Ava <3

#### Usage

    !vote
