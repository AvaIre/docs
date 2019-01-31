# Command List

Below you'll find a list of all **148** commands that Ava has, along with a short description of what each command does. If you'd like to know more about the command, like what permissions or roles are required to run the command, different aliases or anything similar you can click on the command links and you'll be taken to a more descriptive version of the command, or use the help command for the given command in a Discord server.

> {tip} All commands can be used by mentioning Ava first, followed by the command you want to run, for example `@AvaIre ping` will run the ping command, or `@AvaIre poke @Senither` will run the poke command for Senither.

## Table of Contents

- [Help Command](#help)
- [Administration](#administration)
- [Fun](#fun)
- [Interaction](#interaction)
- [Music](#music)
- [Search](#search)
- [Utility](#utility)

<a name="help"></a>
## Help Command

| Command           | Short Description      |
| ----------------- |:---------------------- |
| [!help](/docs/{{version}}/commands#HelpCommand)  | Lists all the command modules  |
| [!help [category]](/docs/{{version}}/commands#HelpCommand)  | Lists all the commands in the given category  |
| [!help [command]](/docs/{{version}}/commands#HelpCommand)  | Displays information about the provided command  |

> You can display all the commands in a category by just typing the first letters of the category, so displaying all the commands in the `administration` category can be done by just typing `!help ad`

<a name="administration"></a>
## Administration

| Command | Short Description |
| ------- |:----------------- |
| [!alr](/docs/{{version}}/commands#AddLevelRoleCommand) | Adds a role to the leveling up table, roles on the table will be given to users once they level up and meet the requirements for the role. |
| [!arr](/docs/{{version}}/commands#AddReactionRoleCommand) | Adds a reaction emote to the last message sent in the channel, and attaches a role to the emote, users can then reaction to the message using the emote to get the role linked with the emote. |
| [!asar](/docs/{{version}}/commands#AddSelfAssignableRoleCommand) | Adds a role to the self-assignable roles list, any role on the list can be claimed by users when they use `:prefixiam <role>`. |
| [!ai](/docs/{{version}}/commands#AiCommand) | Toggles the AI(Artificial Intelligence) on/off for the current channel. |
| [!alias](/docs/{{version}}/commands#AliasCommand) | Creates and maps a custom alias for a pre-existing command. Provide no alias to remove an existing alias. |
| [!autorole](/docs/{{version}}/commands#AutoAssignRoleCommand) | Automatically assigns a specified role to every user who joins the server. |
| [!ban](/docs/{{version}}/commands#BanCommand) | Bans the mentioned user from the server with the provided reason, all messages the user has sent in the last 7 days will also be deleted in the process, this action will be reported to any channel that has modloging enabled. |
| [!categories](/docs/{{version}}/commands#CategoriesCommand) | Shows status of all command categories in the current or mentioned channel, both for globally and per-channel. |
| [!changeprefix](/docs/{{version}}/commands#ChangePrefixCommand) | Sets the prefix that should be used for all commands in a given category, if no prefix is provided the category prefix will be reset back to the default instead, each category in AvaIre can have a different prefix, or you can choose to change them all at the same time. |
| [!channellevel](/docs/{{version}}/commands#ChannelLevelCommand) | Toggles XP rewards on or off for the mentioned channel, if no arguments is given the channels that currently has their channel rewards disabled will be displayed instead, the command can be used to prevent rewarding users experience in certain channels like #spam channels. |
| [!goodbye](/docs/{{version}}/commands#GoodbyeCommand) | Toggles the goodbye messages on or off for the current channel. |
| [!goodbyemessage](/docs/{{version}}/commands#GoodbyeMessageCommand) | Sets the message that should be sent when a user leaves the server, this command can only be used if the goodbye module is enabled for the current channel. |
| [!iam](/docs/{{version}}/commands#IAmCommand) | Gives you the role with the given name if it is in the self-assignable list of roles. |
| [!iamnot](/docs/{{version}}/commands#IAmNotCommand) | Removes the role with the given name from you if it is in the self-assignable list of roles. |
| [!kick](/docs/{{version}}/commands#KickCommand) | Kicks the mentioned user from the server with the provided reason, this action will be reported to any channel that has modloging enabled. |
| [!language](/docs/{{version}}/commands#LanguageCommand) | Show a list of available languages or set a language that should be used for the server. |
| [!levelalerts](/docs/{{version}}/commands#LevelAlertsCommand) | Toggles the Leveling alerts system on or off for the current server or channel. |
| [!togglelevel](/docs/{{version}}/commands#LevelCommand) | Toggles the Leveling system on or off for the current server. |
| [!levelhierarchy](/docs/{{version}}/commands#LevelHierarchyCommand) | Level Hierarchy determines if level roles give to users should be removed once they level up and get the next role, or if they should keep all of their roles, when the level hierarchy is enabled and a user levels up to get the next role, all other level roles they have will be removed, if they level up to a level without a level role, nothing will happen to them, the feature can be toggled on and off using this command. |
| [!levelmodifier](/docs/{{version}}/commands#LevelModifierCommand) | The level modifier allows a server to set a custom level and experience modifier, allowing a server to fine tune the amount of XP required to level up by either making it harder or easier than default. |
| [!aliases](/docs/{{version}}/commands#ListAliasesCommand) | Lists all the existing command aliases. |
| [!llr](/docs/{{version}}/commands#ListLevelRolesCommand) | List all the leveling roles and the level require to get them. |
| [!lrr](/docs/{{version}}/commands#ListReactionRoleCommand) | List reaction messages with a snippet of the message, along with what roles and emotes are linked to the message. |
| [!lsar](/docs/{{version}}/commands#ListSelfAssignableRolesCommand) | List all the self-assignable roles, 10 per-page. |
| [!modlog](/docs/{{version}}/commands#ModlogCommand) | Displays the modlogging status for the server if no arguments is given, you can also mention a text channel to enable modlogging and set it to the mentioned channel. |
| [!modloghistory](/docs/{{version}}/commands#ModlogHistoryCommand) | Displays the modlog history for the mentioned user, this will display all past warnings, bans, soft bans, kicks, and voice kicks. |
| [!pardon](/docs/{{version}}/commands#ModlogPardonCommand) | Pardons the given modlog case ID, removing it from the users modlog history log and locking the message so it can't be edited. |
| [!reason](/docs/{{version}}/commands#ModlogReasonCommand) | Sets the reason for an old modlog case, this command requires the server has a modlog channel set using the `!modlog` command. |
| [!nsfw](/docs/{{version}}/commands#NSFWCommand) | Displays the NSFW status of the current channel, additionally on/off can be passed to the command to change the channels NSFW status. |
| [!purge](/docs/{{version}}/commands#PurgeCommand) | Deletes up to 100 chat messages in any channel, you can mention a user if you only want to delete messages by the mentioned user. |
| [!rlr](/docs/{{version}}/commands#RemoveLevelRoleCommand) | Remove a role from the leveling up role table. |
| [!rrr](/docs/{{version}}/commands#RemoveReactionRoleCommand) | Removes a reaction message and all of its reaction roles, or removes just a single reaction role from a reaction message. |
| [!rsar](/docs/{{version}}/commands#RemoveSelfAssignableRoleCommand) | Removes a role from the self-assignable roles list, any role on the list can be claimed by users when they use `:prefixiam <role>`. |
| [!slowmode](/docs/{{version}}/commands#SlowmodeCommand) | Disables the slowmode or enables it with the given limit, users with the **Manage Messages**  or **Manage Channels** permissions are exempt from slowmode limits. |
| [!softban](/docs/{{version}}/commands#SoftBanCommand) | Bans the mentioned user from the server with the provided reason without removing any of the messages they have sent, this action will be reported to any channel that has modloging enabled. |
| [!togglecategory](/docs/{{version}}/commands#ToggleCategoryCommand) | This command allows you to toggle command categories on/off for the current channel or the whole server in one go, this is useful if you like some features in the bot but not others. |
| [!unban](/docs/{{version}}/commands#UnbanCommand) | Unbans the user with the given ID from the server if they are banned, if a modlog channel is setup, the unban will be logged to the channel as well. |
| [!voicekick](/docs/{{version}}/commands#VoiceKickCommand) | Kicks the mentioned user from the voice channel they're currently connected to, this action will be reported to any channel that has modloging enabled. |
| [!warn](/docs/{{version}}/commands#WarnCommand) | Warns a given user with a message, this action will be reported to any channel that has modloging enabled. |
| [!welcome](/docs/{{version}}/commands#WelcomeCommand) | Toggles the welcome messages on or off for the current channel. |
| [!welcomemessage](/docs/{{version}}/commands#WelcomeMessageCommand) | Sets the message that should be sent when a user joins the server, this command can only be used if the welcome module is enabled for the current channel. |

<a name="fun"></a>
## Fun

| Command | Short Description |
| ------- |:----------------- |
| [!chucknorris](/docs/{{version}}/commands#ChuckNorrisCommand) | I will get a random 100% true, real facts about Chuck Norris for you using the "Internet Chuck Norris Database". |
| [!coinflip](/docs/{{version}}/commands#CoinflipCommand) | Flips a coin heads or tails. |
| [!dice](/docs/{{version}}/commands#DiceCommand) | Rolls a dice or multiple dice with the given number of sides. |
| [!8ball](/docs/{{version}}/commands#EightBallCommand) | Ask 8Ball a question and get a random response back. |
| [!flip](/docs/{{version}}/commands#FlipTextCommand) | Flips the given message upside down. |
| [!lenny](/docs/{{version}}/commands#LennyCommand) | ( ͡° ͜ʖ ͡°) |
| [!meme](/docs/{{version}}/commands#MemeCommand) | Generates memes with your given text, you can tag users to use their avatar as a meme, or just give the meme name you wanna use. |
| [!randomcat](/docs/{{version}}/commands#RandomCatCommand) | I will scour the internet to find a random cat picture for you. |
| [!randomdog](/docs/{{version}}/commands#RandomDogCommand) | I will scour the internet to find a random dog picture for you. |
| [!repeat](/docs/{{version}}/commands#RepeatCommand) | I will repeat anything you say. |
| [!reverse](/docs/{{version}}/commands#ReverseCommand) | Reverses the message given. |
| [!rip](/docs/{{version}}/commands#RipCommand) | Pay your respects |
| [!roll](/docs/{{version}}/commands#RollCommand) | Roll a random number between 1 and 100, or within the given parameters. |
| [!say](/docs/{{version}}/commands#SayCommand) | I will say whatever you tell me to. |
| [!undertale](/docs/{{version}}/commands#UndertaleTextBoxCommand) | Create your own Undertale text boxes with any character and text you want, you can also specify a image through a URL that should be used as the avatar instead.! |

<a name="interaction"></a>
## Interaction

| Command | Short Description |
| ------- |:----------------- |
| [!bite](/docs/{{version}}/commands#BiteCommand) | Sends the **bite** interaction to the mentioned user. |
| [!blush](/docs/{{version}}/commands#BlushCommand) | Sends the **blush** interaction to the mentioned user. |
| [!cuddle](/docs/{{version}}/commands#CuddleCommand) | Sends the **cuddle** interaction to the mentioned user. |
| [!divorce](/docs/{{version}}/commands#DivorceCommand) | Sends the **divorce** interaction to the mentioned user. |
| [!eats](/docs/{{version}}/commands#EatCommand) | Sends the **eats** interaction to the mentioned user. |
| [!hello](/docs/{{version}}/commands#HelloCommand) | Sends the **hello** interaction to the mentioned user. |
| [!highfive](/docs/{{version}}/commands#HighFiveCommand) | Sends the **highfive** interaction to the mentioned user. |
| [!hug](/docs/{{version}}/commands#HugCommand) | Sends the **hug** interaction to the mentioned user. |
| [!kill](/docs/{{version}}/commands#KillCommand) | Sends the **kill** interaction to the mentioned user. |
| [!kiss](/docs/{{version}}/commands#KissCommand) | Sends the **kiss** interaction to the mentioned user. |
| [!marryme](/docs/{{version}}/commands#MarryCommand) | Sends the **marryme** interaction to the mentioned user. |
| [!pan](/docs/{{version}}/commands#PanCommand) | Sends the **pan** interaction to the mentioned user. |
| [!pat](/docs/{{version}}/commands#PatCommand) | Sends the **pat** interaction to the mentioned user. |
| [!poke](/docs/{{version}}/commands#PokeCommand) | Sends the **poke** interaction to the mentioned user. |
| [!pouts](/docs/{{version}}/commands#PoutCommand) | Sends the **pouts** interaction to the mentioned user. |
| [!punch](/docs/{{version}}/commands#PunchCommand) | Sends the **punch** interaction to the mentioned user. |
| [!senpai](/docs/{{version}}/commands#SenpaiCommand) | Sends the **senpai** interaction to the mentioned user. |
| [!shrugs](/docs/{{version}}/commands#ShrugCommand) | Sends the **shrugs** interaction to the mentioned user. |
| [!slap](/docs/{{version}}/commands#SlapCommand) | Sends the **slap** interaction to the mentioned user. |
| [!tickle](/docs/{{version}}/commands#TickleCommand) | Sends the **tickle** interaction to the mentioned user. |
| [!triggered](/docs/{{version}}/commands#TriggeredCommand) | Sends the **triggered** interaction to the mentioned user. |

<a name="music"></a>
## Music

| Command | Short Description |
| ------- |:----------------- |
| [!clearqueue](/docs/{{version}}/commands#ClearQueueCommand) | Clears the music queue of all pending songs |
| [!djlevel](/docs/{{version}}/commands#DJLevelCommand) | Change the DJ level requirement for the server, this changes what music commands people can use with or without the `DJ` Discord role. |
| [!movehere](/docs/{{version}}/commands#MoveHereCommand) | Moves the bot to your current voice channel. |
| [!musicchannel](/docs/{{version}}/commands#MusicChannelCommand) | The music channel command can be used to define a text and voice channel that music should be linked to, if a text channel is set through the command, music commands will only work in the given channel, if a voice channel is set Ava will auto join the voice channel on the first music request. |
| [!musicmessages](/docs/{{version}}/commands#MusicMessagesCommand) | Toggles music messages on and off, when music messages are off, the "Now Playing" messages will no longer be sent, and messages that before would stay, will now be automatically be deleted after awhile.  |
| [!pause](/docs/{{version}}/commands#PauseCommand) | Pauses the music currently playing |
| [!play](/docs/{{version}}/commands#PlayCommand) | Plays the provided song for you, if just the song title is given the bot will search YouTube for your song and give you some suggestions, you can also use YouTube, SoundCloud, TwitchTV, Bandcamp, and Vimeo link, or raw sound file, mp3, flac, wav, webm, mp4, ogg, aac, m3u and pls formats. |
| [!playlist](/docs/{{version}}/commands#PlaylistCommand) | Music playlist command, allows music DJs to create, delete, and load playlists to the music queue, as well as adding and removing songs from any of the playlists. |
| [!removesong](/docs/{{version}}/commands#RemoveSongFromQueueCommand) | Removes a song or multiple songs from the music queue. |
| [!repeatsongs](/docs/{{version}}/commands#RepeatMusicQueueCommand) | Repeats all the songs in the music queue. |
| [!resume](/docs/{{version}}/commands#ResumeCommand) | Resumes the music in the queue, starting the music back up if it was paused |
| [!seek](/docs/{{version}}/commands#SeekCommand) | Jumps to the given time code in the track that is currently playing. |
| [!default-volume](/docs/{{version}}/commands#SetDefaultVolumeCommand) | Sets the default volume that the music should play at when Ava first joins a voice channel. |
| [!shuffle](/docs/{{version}}/commands#ShuffleCommand) | Shuffles the music queue, mixing the songs up in random order. |
| [!skip](/docs/{{version}}/commands#SkipCommand) | Skips to the next song in the music queue. |
| [!song](/docs/{{version}}/commands#SongCommand) | Returns the song that is playing right now and some attached information. This includes who requested it, how much of the song is left and the volume the song is playing at plus the rest of the songs currently in queue. |
| [!soundcloud](/docs/{{version}}/commands#SoundcloudCommand) | Plays the provided song for you, if just the song title is given the bot will search SoundCloud for your song and give you some suggestions, you can also use YouTube, SoundCloud, TwitchTV, Bandcamp, and Vimeo link, or raw sound file, mp3, flac, wav, webm, mp4, ogg, aac, m3u and pls formats. |
| [!stop](/docs/{{version}}/commands#StopCommand) | Stops the song currently playing, clears the music queue and disconnects from the voice channel the music was playing in. |
| [!voicefix](/docs/{{version}}/commands#VoiceFixCommand) | Music will sometimes stop working when Discord forgets to notify bots about voice state changes, this commands tries to make fixing that a bit easier to do by forcing a voice update state for the bot through changing the server region, the command will pick a server region at random, swap the servers region to that, and then 2½ seconds later swap right back, this should fix music 99% of the time. |
| [!volume](/docs/{{version}}/commands#VolumeCommand) | Changes the volume of the music, by default the music will be playing at 100% volume. |
| [!voteskip](/docs/{{version}}/commands#VoteSkipCommand) | Use this command to vote on the song currently playing to be skipped, if the vote wins with a majority vote the song will be skipped. |

<a name="search"></a>
## Search

| Command | Short Description |
| ------- |:----------------- |
| [!duckduckgo](/docs/{{version}}/commands#DuckDuckGoCommand) | Searches [DuckDuckGo.com](https://duckduckgo.com/) with the given query and returns the first six results, if the command is used in a channel with NSFW disabled, all NSFW search results will be removed from the results. |
| [!gfycat](/docs/{{version}}/commands#GfycatCommand) | Returns a random gif for you from gfycat.com with the given query. |
| [!urbandictionary](/docs/{{version}}/commands#UrbanDictionaryCommand) | Get the definition of a word or sentence from [urbandictionary.com](https://www.urbandictionary.com/). |
| [!xkcd](/docs/{{version}}/commands#XKCDCommand) | Gets the latest XKCD comic, or the comic with the given id. |

<a name="utility"></a>
## Utility

| Command | Short Description |
| ------- |:----------------- |
| [!calculate](/docs/{{version}}/commands#CalculateCommand) | Calculates the given math equations and returns the result for you. |
| [!channelid](/docs/{{version}}/commands#ChannelIdCommand) | Shows the ID of the channel the command was ran in, or the channel tagged in the command. |
| [!channelinfo](/docs/{{version}}/commands#ChannelInfoCommand) | Shows information about the channel the command was run in, or the mentioned channel. |
| [!expand](/docs/{{version}}/commands#ExpandUrlCommand) | Expands the url to the full form, resolving all the redirects and showing what urls the link goes through if it redirects anywhere. |
| [!feedback](/docs/{{version}}/commands#FeedbackCommand) | Send feedback about Ava back to the developers and the staff team, any message passed to the command will be sent in the [#feedback](https://discord.gg/gt2FWER) channel on the [AvaIre Central](https://discord.gg/gt2FWER) server. |
| [!gleaderboard](/docs/{{version}}/commands#GlobalLeaderboardCommand) | Shows the top 100 users globally, combining their rank, level, and xp between all servers the users are on. |
| [!ipinfo](/docs/{{version}}/commands#IPInfoCommand) | Gives information about the given IP address. |
| [!invite](/docs/{{version}}/commands#InviteCommand) | Returns a link that can be used to invite the bot to other servers. |
| [!leaderboard](/docs/{{version}}/commands#LeaderboardCommand) | Displays the server's level leaderboard with the user's name, rank, level and XP. The response is paginated to show 10 users per page. |
| [!ping](/docs/{{version}}/commands#PingCommand) | Can be used to check if the bot is still alive. |
| [!backgrounds](/docs/{{version}}/commands#RankBackgroundCommand) | Rank backgrounds are used for the `!rank` command, when a user has a rank |
| [!rank](/docs/{{version}}/commands#RankCommand) | Gets your rank, level, xp for the current server and total xp for all servers that you're on, you can tag a user to see their level stats instead. |
| [!remindme](/docs/{{version}}/commands#RemindCommand) | Reminds you of something after a certain amount of time. |
| [!serverid](/docs/{{version}}/commands#ServerIdCommand) | Shows the ID of the server the command was ran in. |
| [!serverinfo](/docs/{{version}}/commands#ServerInfoCommand) | Shows information about the server the command was ran in. |
| [!source](/docs/{{version}}/commands#SourceCommand) | Gives you the source code for the Bot, or the code for a given command. |
| [!stats](/docs/{{version}}/commands#StatsCommand) | Displays information about Ava and some related stats. |
| [!uptime](/docs/{{version}}/commands#UptimeCommand) | Displays how long the bot has been online for. |
| [!avatar](/docs/{{version}}/commands#UserAvatarCommand) | Get the profile picture of someone on the server by name, id, or mentions. |
| [!userid](/docs/{{version}}/commands#UserIdCommand) | Shows your Discord account user ID, or the ID of the user tagged in the command. |
| [!userinfo](/docs/{{version}}/commands#UserInfoCommand) | Shows information about the user that ran the command, or the mentioned user. This includes the users username, ID, roles, the date they joined the server, the date they created their account, and how many servers they're in (That Ava knows about). |
| [!version](/docs/{{version}}/commands#VersionCommand) | Displays the current version of Ava that is running. If the version is outdated the new version will be shown as well as what type of changes have been made. |
| [!vote](/docs/{{version}}/commands#VoteCommand) | Enjoy using the bot? Consider voting for the bot to help it grow, it's free but means a lot to the team behind Ava <3 |
