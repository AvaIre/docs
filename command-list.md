# Command List

Below you'll find a list of all **128** commands that Ava has, along with a short description of what each command does. If you'd like to know more about the command, like what permissions or roles are required to run the command, different aliases or anything similar you can click on the command links and you'll be taken to a more descriptive version of the command, or use the help command for the given command in a Discord server.

> All commands can be used by mentioning Ava first, followed by the command you want to run, for example `@AvaIre ping` will run the ping command, or `@AvaIre poke @Senither` will run the poke command for Senither.

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

| Command           | Short Description      |
| ----------------- |:---------------------- |
| [!ai](/docs/{{version}}/commands#AiCommand)  | Toggles the AI on or off for the current channel  |
| [!alias [alias] [command]](/docs/{{version}}/commands#AliasCommand)  | Binds or unbinds custom command aliases  |
| [!aliases [page]](/docs/{{version}}/commands#ListAliasesCommand)  | Lists all command aliases for the server  |
| [!alr <level requirement\> <role\>](/docs/{{version}}/commands#AddLevelRoleCommand)  | Adds a level role to the leveling up table   |
| [!asar <role\>](/docs/{{version}}/commands#AddSelfAssignableRoleCommand)  | Adds a  role to the self-assignable roles list  |
| [!autorole <role\>](/docs/{{version}}/commands#AutoAssignRoleCommand)  | Auto assigns a specified role to every user who joins the server  |
| [!avatar](/docs/{{version}}/commands#UserAvatarCommand)  | Get the profile picture of someone on the server by name, id, or mentions.  |
| [!ban <user\> [reason]](/docs/{{version}}/commands#BanCommand)  | Bans the tagged user with the given reason  |
| [!categories](/docs/{{version}}/commands#CategoriesCommand)  | Shows the status for all the command categories for the current channel, and globally  |
| [!changeprefix <module\> [prefix]](/docs/{{version}}/commands#ChangePrefixCommand)  | Changes the prefix Ava uses  |
| [!djlevel](/docs/{{version}}/commands#DJLevelCommand)  | Change the DJ level requirement for the server  |
| [!goodbye](/docs/{{version}}/commands#GoodbyeCommand)  | Toggles the goodbye module on or off for the current channel  |
| [!goodbyemessage [message]](/docs/{{version}}/commands#GoodbyeMessageCommand)  | Sets the goodbye message for the current channel  |
| [!iam <role\>](/docs/{{version}}/commands#IAmCommand)  | Gives the user the role with the given name if it is claimable  |
| [!iamnot <role\>](/docs/{{version}}/commands#IAmNotCommand)  | Takes a role from the user with the given name if it is claimable  |
| [!kick <user\> [reason]](/docs/{{version}}/commands#KickCommand)  | Kicks the tagged user from the server  |
| [!language <lang\>](/docs/{{version}}/commands#LanguageCommand)  | Changes the language that Ava uses  |
| [!togglelevel](/docs/{{version}}/commands#LevelCommand)  | Toggles the level system on or off for the current server  |
| [!levelalerts [channel]](/docs/{{version}}/commands#LevelAlertsCommand)  | Toggles the level alerts system on or off for the current server  |
| [!llr [page]](/docs/{{version}}/commands#ListLevelRolesCommand)  | List all the level roles, 10 per-page  |
| [!lsar [page]](/docs/{{version}}/commands#ListSelfAssignableRolesCommand)  | List all the self-assignable roles, 10 per-page  |
| [!nsfw](/docs/{{version}}/commands#NSFWCommand)  | Displays the NSFW status of the current channel  |
| [!modlog \[channel\]](/docs/{{version}}/commands#ModlogCommand)  | Displays the modlog status and toggles it on/off  |
| [!modloghistory <user\>](/docs/{{version}}/commands#ModlogHistoryCommand)  | Displays the modlog history for the user  |
| [!purge <amount\> [user]](/docs/{{version}}/commands#PurgeCommand)  | Purge old messages from the current channel  |
| [!reason <case id\> <reason\>](/docs/{{version}}/commands#ModlogReasonCommand)  | Changes the reason for the given modlog case id  |
| [!rlr <role/level\>](/docs/{{version}}/commands#RemoveLevelRoleCommand)  | Removes the level role from the level table roles list  |
| [!rsar <role\>](/docs/{{version}}/commands#RemoveSelfAssignableRoleCommand)  | Removes the role from the self-assignable roles list  |
| [!slowmode [limit] [decay]](/docs/{{version}}/commands#SlowmodeCommand)  | Toggles slowmode on or off for the current channel  |
| [!softban <user\> [reason]](/docs/{{version}}/commands#SoftBanCommand)  | Bans the tagged user with the given reason  |
| [!togglecategory <category\> <channel\>](/docs/{{version}}/commands#ToggleCategoryCommand)  |  Toggles the given category on or off for the current channel or the whole server  |
| [!voicekick <user\>](/docs/{{version}}/commands#VoiceKickCommand)  | Kicks the mentioned user from the voice channel  |
| [!warn <user\> [reason]](/docs/{{version}}/commands#WarnCommand)  | Warns the user with the given message  |
| [!welcome](/docs/{{version}}/commands#WelcomeCommand)  | Toggles the welcome module on or off for the current channel  |
| [!welcomemessage](/docs/{{version}}/commands#WelcomeMessageCommand)  | Sets the welcome message for the current channel  |

<a name="fun"></a>
## Fun

| Command           | Short Description      |
| ----------------- |:---------------------- |
| [!8ball](/docs/{{version}}/commands#EightBallCommand)  | Ask 8Ball a question  |
| [!chucknorris](/docs/{{version}}/commands#ChuckNorrisCommand)  | Gets a random 100% true fact about Chuck Norris  |
| [!coin](/docs/{{version}}/commands#CoinflipCommand)  | Flips a coin for heads or tails  |
| [!dice [dice format]](/docs/{{version}}/commands#DiceCommand)  | Rolls a set of dice  |
| [!flip [message]](/docs/{{version}}/commands#FlipTextCommand)  | Flips the given message upside down.  |
| [!lenny](/docs/{{version}}/commands#LennyCommand)  | ( ͡° ͜ʖ ͡°)  |
| [!meme <meme\> [top text] [bottom text]](/docs/{{version}}/commands#MemeCommand)  | Creates a custom meme of the given type  |
| [!cat](/docs/{{version}}/commands#RandomCatCommand)  | Gets a random cat image from the internet  |
| [!dog](/docs/{{version}}/commands#RandomDogCommand)  | Gets a random dog image from the internet  |
| [!repeat [message]](/docs/{{version}}/commands#RepeatCommand)  | Makes Ava repeat whatever you say  |
| [!reverse [message]](/docs/{{version}}/commands#ReverseCommand)  | Reverses the message given.  |
| [!rip](/docs/{{version}}/commands#RipCommand)  | Pay your respects  |
| [!roll [min] [max]](/docs/{{version}}/commands#RollCommand)  | Rolls a random number between 1 and 100, or between the numbers given  |
| [!say [message]](/docs/{{version}}/commands#SayCommand)  | Makes Ava say whatever you want  |

<a name="interaction"></a>
## Interaction

| Command           | Short Description      |
| ----------------- |:---------------------- |
| [!bite <user\>](/docs/{{version}}/commands#interaction-commands)  | Bites the mentioned user  |
| [!cuddle <user\>](/docs/{{version}}/commands#interaction-commands)  | Cuddles the mentioned user  |
| [!divorce <user\>](/docs/{{version}}/commands#interaction-commands)  | Divorces the mentioned user  |
| [!eats <user\>](/docs/{{version}}/commands#interaction-commands)  | Eats some food with the mentioned user  |
| [!hello <user\>](/docs/{{version}}/commands#interaction-commands)  | Says hello to the mentioned user  |
| [!highfive <user\>](/docs/{{version}}/commands#interaction-commands)  | High fives the mentioned user  |
| [!hug <user\>](/docs/{{version}}/commands#interaction-commands)  | Hugs the mentioned user  |
| [!kill <user\>](/docs/{{version}}/commands#interaction-commands)  | Kills the mentioned user  |
| [!kiss <user\>](/docs/{{version}}/commands#interaction-commands)  | Kisses the mentioned user  |
| [!pan <user\>](/docs/{{version}}/commands#interaction-commands)  | Hits the mentioned user with a pan  |
| [!pat <user\>](/docs/{{version}}/commands#interaction-commands)  | Pats the mentioned user  |
| [!poke <user\>](/docs/{{version}}/commands#interaction-commands)  | Pokes the mentioned user  |
| [!pouts <user\>](/docs/{{version}}/commands#interaction-commands)  | Pouts at the mentioned user  |
| [!punch <user\>](/docs/{{version}}/commands#interaction-commands)  | Punches at the mentioned user  |
| [!senpai <user\>](/docs/{{version}}/commands#interaction-commands)  | Sends an image in hope that the mentioned user notice you |
| [!shrug <user\>](/docs/{{version}}/commands#interaction-commands)  | Shrugs at the mentioned user  |
| [!slap <user\>](/docs/{{version}}/commands#interaction-commands)  | Slaps the mentioned user  |
| [!tickle <user\>](/docs/{{version}}/commands#interaction-commands)  | Tickles the mentioned user  |
| [!triggered <user\>](/docs/{{version}}/commands#interaction-commands)  | Sends an image to let the mentioned user know you're triggered  |

<a name="music"></a>
## Music

| Command           | Short Description      |
| ----------------- |:---------------------- |
| [!clearqueue](/docs/{{version}}/commands#ClearQueueCommand)  | Clears the music queue of all pending songs  |
| [!default-volume](/docs/{{version}}/commands#SetDefaultVolumeCommand)  | Sets the default volume used by all the music  |
| [!movehere](/docs/{{version}}/commands#MoveHereCommand)  | Moves the bot into the same voice channel you're in  |
| [!musicchannel <type\> <channel\>](/docs/{{version}}/commands#MusicChannelCommand)  | Set the channel that should be used for music  |
| [!musicmessages <on/off\>](/docs/{{version}}/commands#MusicMessagesCommand)  | Toggle music messages on/off  |
| [!pause](/docs/{{version}}/commands#PauseCommand)  | Pauses the song that is currently playing  |
| [!play <song\>](/docs/{{version}}/commands#PlayCommand)  | Adds the given song to the queue from YouTube, or by link  |
| [!playlist](/docs/{{version}}/commands#PlaylistCommand)  | Main command used to manage the custom music playlists  |
| [!removesong](/docs/{{version}}/commands#RemoveSongFromQueueCommand)  | Removes a song from the music queue  |
| [!repeatsongs](/docs/{{version}}/commands#RepeatMusicQueueCommand)  | Repeats the songs currently in the music queue  |
| [!resume](/docs/{{version}}/commands#ResumeCommand)  | Resumes the song that was playing before  |
| [!seek <time\>](/docs/{{version}}/commands#SeekCommand)  | Jumps to the given time in the song currently playing  |
| [!shuffle](/docs/{{version}}/commands#ShuffleCommand)  | Shuffles the songs waiting in the queue  |
| [!skip](/docs/{{version}}/commands#SkipCommand)  | Skips the song that is currently playing  |
| [!songs](/docs/{{version}}/commands#SongCommand)  | Lists all the songs in the music queue  |
| [!soundcloud <song\>](/docs/{{version}}/commands#SoundcloudCommand)  | Adds the given song to the queue from Soundcloud, or by link  |
| [!stop](/docs/{{version}}/commands#StopCommand)  | Stops the music and disconnects from voice  |
| [!volume <vol\>](/docs/{{version}}/commands#VolumeCommand)  | Changes the volume of the music  |
| [!voteskip](/docs/{{version}}/commands#VoteSkipCommand)  | Votes to skip the song that is currently playing  |

<a name="search"></a>
## Search

| Command           | Short Description      |
| ----------------- |:---------------------- |
| [!g <query\>](/docs/{{version}}/commands#DuckDuckGoCommand)  | Searches DuckDuckGo.com with your given query  |
| [!gfycat [tags]](/docs/{{version}}/commands#GfycatCommand)  | Gets a random gif from [gfycat.com](https://gfycat.com/)  |
| [!urban [word]](/docs/{{version}}/commands#UrbanDictionaryCommand)  | Get the definition of a word or sentence from [urbandictionary.com](http://www.urbandictionary.com/)  |
| [!xkcd [number]](/docs/{{version}}/commands#XKCDCommand)  | Gets the latest [xkcd](https://xkcd.com/) comic, or the comic with the given id.  |

<a name="utility"></a>
## Utility

| Command           | Short Description      |
| ----------------- |:---------------------- |
| [!calc <url\>](/docs/{{version}}/commands#CalculateCommand)  | Calculates the given math equations and returns the result for you  |
| [!channelid](/docs/{{version}}/commands#ChannelIdCommand)  | Displays the status of modules for the current channel  |
| [!channelinfo](/docs/{{version}}/commands#ChannelInfoCommand)  | Displays the status of modules for the current channel  |
| [!expand <url\>](/docs/{{version}}/commands#ExpandUrlCommand)  | Unshorten an URL  |
| [!feedback <msg\>](/docs/{{version}}/commands#FeedbackCommand)  | Gives feedback about the bot  |
| [!gleaderboard](/docs/{{version}}/commands#GlobalLeaderboardCommand)  | Shows the top 100 users globally, combining their rank, level, and xp between all servers the users are on.  |
| [!invite](/docs/{{version}}/commands#InviteCommand)  | Sends the link to invite Ava to your server  |
| [!ipinfo <address\>](/docs/{{version}}/commands#IPInfoCommand)  | Gives information about the given IP address  |
| [!leaderboard](/docs/{{version}}/commands#LeaderboardCommand)  | Sends the level leaderboard for the current server  |
| [!ping](/docs/{{version}}/commands#PingCommand)  | Ping, Pong  |
| [!rank](/docs/{{version}}/commands#RankCommand)  | Displays the users rank, level and XP if Leveling is enabled  |
| [!remindme <args\>](/docs/{{version}}/commands#RemindCommand)  | Set a message you would like to be reminded about  |
| [!serverid](/docs/{{version}}/commands#ServerIdCommand)  | Shows the server ID |
| [!serverinfo](/docs/{{version}}/commands#ServerInfoCommand)  | Shows information about the server  |
| [!shards](/docs/{{version}}/commands#ShardCommand)  | Displays the bot shards, or the stats command if no shards are used  |
| [!source](/docs/{{version}}/commands#SourceCommand)  | Sends a link to the source code for the given command  |
| [!stats](/docs/{{version}}/commands#StatsCommand)  | Displays information and stats about Ava  |
| [!uptime](/docs/{{version}}/commands#UptimeCommand)  | Displays how long Ava has been online for  |
| [!userid [user]](/docs/{{version}}/commands#UserIdCommand)  | Shows the ID of the tagged user  |
| [!userinfo [user]](/docs/{{version}}/commands#UserInfoCommand)  | Shows information about the tagged user  |
| [!version](/docs/{{version}}/commands#VersionCommand)  | Displays the current version of Ava  |
| [!vote](/docs/{{version}}/commands#VoteCommand)  | Links a site where you can vote for rewards  |
