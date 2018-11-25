# Linux Guide

- [Prerequisites](#prerequisites)
    - [Linux Server](#server)
    - [Software](#software)
- [Installing Requirements](#install-requirements)
    - [Java 10](#install-java)
    - [Gradle - Build](#install-gradle)
    - [Git - Source Control](#install-git)
- [MySQL](#install-mysql)
- [Installing Ava](#install-ava)
- [Configuration of Ava](#configuration)
- [Running the bot](#running-the-bot)
- [System Commands](#system-commands)
    - [Blacklist Command](#BlacklistCommand)
    - [Bot Statistics Command](#BotStatisticsCommand)
    - [Debug Mode Command](#DebugModeCommand)
    - [Eval Command](#EvalCommand)
    - [Feedback Response Command](#FeedbackResponseCommand)
    - [Force Leave Server Command](#ForceLeaveServerCommand)
    - [JSON Command Map](#JSONCmdMapCommand)
    - [Partner Command](#PartnerCommand)
    - [Plugin Command](#PluginCommand)
    - [Reload Configuration Command](#ReloadCommand)
    - [Restart Command](#RestartCommand)
    - [Set Guild Type Command](#SetGuildTypeCommand)
    - [Set Status Command](#SetStatusCommand)
    - [Shutdown Command](#ShutdownCommand)
    - [Update Command](#UpdateCommand)

<a name="prerequisites"></a>
## Prerequisites

> {tip} This guide assumes you already have a basic understanding of Linux based systems and programs like **vim** for editing files in the command line, since the whole guide will be taking place in the command line.

<a name="server"></a>
#### Linux Server

 * __Type:__ A small stable VPS, a dedicated machine is a bit overkill unless you're already using it for other things as well.
 * __OS:__ Ubuntu LTS or latest, optionally Debian 8
 * __Ram:__ May work on 256 MB, 512MB is recommended. If you plan on having it on just a few servers. Scale up if necessary.
 * __Processor:__ Single core @ 2.60 GHz or higher will work just fine, as above.
 * SSH access to the server.

<a name="software"></a>
#### Software

 * SSH client, i.e. [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) connecting and executing commands on the server

<a name="install-requirements"></a>
## Installing Requirements

Start by logging into your server via your SSH client, we will be using [SDKMAN!](https://sdkman.io/) to download, install, and manage things like Gradle and Java so get that first if you don't already have it installed.

    sudo apt install zip unzip
    curl -s "https://get.sdkman.io" | bash
    source "$HOME/.sdkman/bin/sdkman-init.sh"

<a name="install-java"></a>
### Installing Java

We'll be using Java 10+ to run Ava, if you don't already have Java installed, you can install it easily using [SDKMAN!](https://sdkman.io/), first check what versions of Java is available.

    sdk list java

Then pick a version you'd like to use, and install it with.

    sdk install java <version>

> {tip} If you already have Java installed using the OpenJDK, you can uninstall that first by using.
```
apt remove java*
apt autoremove
```

<a name="install-gradle"></a>
### Installing Gradle

We'll be using Gradle 4.7+ to build and compile Ava, if you don't already have Gradle installed, you can install it easily using [SDKMAN!](https://sdkman.io/), first check what versions of Java is available.

    sdk list gradle

Then Gradle itself:

    sdk install gradle <version>

<a name="install-git"></a>
### Installing Git (Optional)

Next we'll install Git to be able to download and update Ava, git will also be used later on if you want to update Ava to the latest version.

Start off by checking if git is already installed, some services that offers Linux servers comes with Git pre-installed, you can check if git is installed by running:

    git --version

If the command is not found you can install git by running

    sudo apt install git

<a name="install-mysql"></a>
## Installing MySQL

> {tip} Ava also supports SQLite, if you want to use the flatfile SQLite database instead, you can skip this step and just tell Ava to use SQLite in the config instead.

We'll need to setup a database that Ava can use. Ava requires a database to store things like custom playlists, aliases, channel and server data, and a lot of other things.

First we need to download MySQL, doing the following:

    sudo apt install mysql-server

Then, go through the basic setup process using:

    mysql_secure_installation

Now, log into your MySQL database as root by typing:  
(It will ask you for your password what you've entered when you installed MySQL on your server.)

    mysql -p

It is time to actually create the database you will be using for your bot. To do this, first choose a good name for it, and type:

    create database <dbname>;

Now, create a username and a password for your new database. The password should be very secure. Type the following:

    grant all privileges on <dbname>.* to '<username>'@'localhost' identified by "<password>";

Where you replace:  
  `<dbname>` with the name of the database you just created,  
  `<username>` with the username you chose  
  `<password>` with the password you chose for your user

Then, type:

    flush privileges;

And finally:

    exit;

<a name="install-ava"></a>
## Installing Ava

Next, we'll need to get the jar file to run Ava, you can get a stable version from the [github releases](https://github.com/avaire/avaire/releases), or the [nightly build](https://avairebot.com/nightly-build.zip) from avairebot.com, the zip file gets updated once every 24 at midnight CEST, you can also build your own jar file by getting source code from the AvaIre GitHub repository, to do this you will will need Git to clone down the code.

You'd want to figure out where you want the bot to be downloaded. When you've found the location of your choice, clone the Ava repository into the folder by using the following command.

    git clone https://github.com/avaire/avaire.git
    cd avaire

You have now successfully cloned the AvaIre Git repository, next we'll need to build the jar file from the source code, we can do this by utilizing gradle which we just installed.

    gradle build

If the build finishes with no errors you should be good to go! You can find the generated binary file at `build/libs/AvaIre.jar`.

<a name="configuration"></a>
## Configuration of Ava

Next we'll need to configure Ava so the bot can connect and communicate with users, to generate the `config.yml` file we'll just need to run Ava once, we can do this by running:

    java -jar AvaIre.jar


You can now open the new `config.yml` file in vim, where you'll need to put your Discord Bot Application token in the `bot.token` property. You can find your bot token under your Discord Application dashboard, if you don't have a Discord bot application setup you can create one easily by following these steps.

 1. Start by heading to [discordapp.com/developers/applications](https://discordapp.com/developers/applications/me), once you're there you can create a new application, you can name it whatever you want and give it a fancy picture and description if you want to, once you're done click **Create App**.
 2. Your application should now have been created, next click on the **Create a Bot User** button, this will convert the application to a bot user application.
 3. Now that you have a user bot application you can get your bot token under the **App Bot User** section.

> {tip} If you want other people to be able to invite the bot you must check the **Public Bot** options under your **App Bot User** application settings, if you don't do that you will be the only one that can invite the bot to servers.

On your bot application dashboard you'll also be able to find your bot client id, we'll need that later to invite the bot so keep onto it.
Now that you're done with that, it's time to fill out the database information, optionally lavalink access, and the client ID's of your bot administrators.

If you want a more in-detail guide and walkover for the [configuration](/docs/{{version}}/configuration) file you can checkout the [Configuration](/docs/{{version}}/configuration) page, all the settings and options are covered in more detail on that page with guides on how to setup each option.

<a name="running-the-bot"></a>
## Running the bot

Congratulations, your AvaIre instance should now be ready to launch!

To start the bot, simply just run the jar file again after editing it with your bot and database details.

    java -jar AvaIre.jar

If the bot runs without any errors, you have had success so far!

> {tip} It is recommend that you run the bot in a separate process to prevent the bot from disconnecting when you disconnect from the machine, screens works pretty well for this.

Now you'll need to invite your bot to your server so you can actually use it, take your bots client id from earlier and pop it into a URL like this without the less than and greater than symbols.

    https://discordapp.com/oauth2/authorize?&client_id=<client id>&scope=bot

Just replace the `<client id>` with your actually bot application id, if you don't have your client id you can find it on the [discordapp.com/developers/applications](https://discordapp.com/developers/applications/me) page, just click on your application, the client ID is at the very top under the **App Details** section.

Go to the URL in a web browser, select your server and hit `Authorize`, your bot should now be on your server.

You can test simple functionality by running the ping command in a text channel that the bot can see. If it answers "Pong!", then congratulations, you have successfully set up AvaIre!

And that's it! You are now ready to start using your very own AvaIre instance!
Keep in mind, if you have further questions or need help, we're around over at our official server, [AvaIre Central](https://discord.gg/gt2FWER)!

On the behalf of the AvaIre team, we hope you enjoy your bot!

<a name="system-commands"></a>
## System Commands

> System commands can only be seen and run by bot administrators, ie, people who have their user ID in the bot admins field in the config of the bot.

All system commands uses a semicolon(;) as their prefix by default.

| Command | Short Description |
| ------- |:----------------- |
| [;blacklist](#BlacklistCommand) | Add, Remove, and list users and servers on the blacklist. |
| [;statistics](#BotStatisticsCommand) | Displays information about the current state of the bot, this command can be pretty heavy to run since a lot of calculations are being run to get some of the information. |
| [;debug-mode](#DebugModeCommand) | Toggles debug mode on/off during runtime, this will enable passing the context between rest actions to give a better debug result, and to make debugging with Sentry more information. |
| [;eval](#EvalCommand) | Evaluates and executes code. |
| [;feedback](#FeedbackResponseCommand) | Responses to a feedback message with the given ID, the channel the original feedback message was sent in will be used for the feedback, along with the message +  the response and author information. |
| [;force-leave](#ForceLeaveServerCommand) | Force leaves a server with the given ID. |
| [;jsoncmdmap](#JSONCmdMapCommand) | Creates a JSON map containing detailed information about each command and stores it in a `commandMap.json` file. |
| [;partner](#PartnerCommand) | Allows a bot admin to change the partnership a server has with the bot, servers who are partnered with the bot has less restrictions and more command slots(Like aliases, self-assignable roles, level roles, playlists, etc), if only the server ID is given the current partnership status will be displayed for the server with the given ID instead.  |
| [;plugin](#PluginCommand) | Can be used to list installed plugins, as well as available plugins that are officially recognized by the AvaIre development team, you can also display more information about a specific plugin by name. |
| [;reload](#ReloadCommand) | Reloads the main configuration, and all the configs for loaded plugins. |
| [;restart](#RestartCommand) | Schedule a time the bot should be automatically-restarted, the bot will shutdown, then start back up again. |
| [;set-type](#SetGuildTypeCommand) | Sets the Guild Type of the server the command was ran in, if no arguments was given the current Guild Type will be displayed instead. |
| [;setstatus](#SetStatusCommand) | Sets the status of the bot instance for all servers the bot is on, if no status is set the bot status will go back to cycling status from the config. |
| [;shutdown](#ShutdownCommand) | Schedules a time the bot should be shutdown gracefully. |
| [;update](#UpdateCommand) | Schedule a time the bot should be automatically-updated, the bot will shutdown, update itself, and start back up again. |

<a name="BlacklistCommand"></a>
### Blacklist Command

Add, Remove, and list users and servers on the blacklist.


#### Usage

    ;blacklist list
    -  Lists users and servers on the blacklist
    ;blacklist remove <id>
    -  Removes the entry with the given ID from the blacklist
    ;blacklist add <type> <id> <reason>
    -  Add the type with the given ID to the blacklist

#### Example

    ;blacklist add G 123
    -  Blacklists the guild with an ID of 123
    ;blacklist add U 321 Doing stuff
    -  Blacklists the user with an ID of 321 for "Doing stuff"

<a name="BotStatisticsCommand"></a>
### Bot Statistics Command

Displays information about the current state of the bot, this command can be pretty heavy to run since a lot of calculations are being run to get some of the information.


#### Usage

    ;statistics
    -  Shows some stats about the bot.


<a name="DebugModeCommand"></a>
### Debug Mode Command

Toggles debug mode on/off during runtime, this will enable passing the context between rest actions to give a better debug result, and to make debugging with Sentry more information.


#### Usage

    ;debug-mode <on|off>
    -  Toggles debug mode on or off

#### Example

    ;debug-mode on
    -  Enables debug mode.

<a name="EvalCommand"></a>
### Eval Command

Evaluates and executes code.


#### Usage

    ;eval <code>
    -  Evaluates and executes the given code.
    ;eval <kill|-k>
    -  Kills the last task if it is still running.
    ;eval <timeout|-t> <timeout lenght> <code>
    -  Evaluates and executes the given code with the given timeout.

#### Example

    ;eval context.makeInfo("Hello, World").queue();
    ;eval -t 10 return "Some Code"

<a name="FeedbackResponseCommand"></a>
### Feedback Response Command

Responses to a feedback message with the given ID, the channel the original feedback message was sent in will be used for the feedback, along with the message +  the response and author information.


#### Usage

    ;feedback <id> <message>
    -  Responds to the given feedback ID with the message.

#### Example

    ;feedback 23 Thanks for the feedback <3

<a name="ForceLeaveServerCommand"></a>
### Force Leave Server Command

Force leaves a server with the given ID.


#### Usage

    ;force-leave <id>
    -  Leaves the server with the given ID if the bot is on the server.

#### Example

    ;force-leave 304414699645042690

<a name="JSONCmdMapCommand"></a>
### JSON Command Map

Creates a JSON map containing detailed information about each command and stores it in a `commandMap.json` file.


#### Usage

    ;jsoncmdmap
    -  Generates the command map and stores it in a file.


<a name="PartnerCommand"></a>
### Partner Command

Allows a bot admin to change the partnership a server has with the bot, servers who are partnered with the bot has less restrictions and more command slots(Like aliases, self-assignable roles, level roles, playlists, etc), if only the server ID is given the current partnership status will be displayed for the server with the given ID instead. 


#### Usage

    ;partner <server ID>
    -  Displays the current guild partnership status.
    ;partner <server ID> <on|off>
    -  Toggles partnership on/off for the given server.

#### Example

    ;partner 284083636368834561
    -  Displays the servers partnerships status.
    ;partner 284083636368834561 enable
    -  Makes the server a partner with Ava.

<a name="PluginCommand"></a>
### Plugin Command

Can be used to list installed plugins, as well as available plugins that are officially recognized by the AvaIre development team, you can also display more information about a specific plugin by name.


#### Usage

    ;plugin show <plugin>
    -  Lists information about the plugin.
    ;plugin list <installed|i> [page]
    -  Lists installed plugins.
    ;plugin list <available|a> [page]
    -  Lists available plugins.


<a name="ReloadCommand"></a>
### Reload Configuration Command

Reloads the main configuration, and all the configs for loaded plugins.




<a name="RestartCommand"></a>
### Restart Command

Schedule a time the bot should be automatically-restarted, the bot will shutdown, then start back up again.
This requires [avaire/watchdog](https://github.com/avaire/watchdog) to work, or that the `--internal-restart` flag was used when starting the bot, without it the bot will just shutdown.


#### Usage

    ;restart now
    -  Restarts the bot now.
    ;restart cancel
    -  Cancels the restart process.
    ;restart <time>
    -  Schedules a time the bot should be restarted.


<a name="SetGuildTypeCommand"></a>
### Set Guild Type Command

Sets the Guild Type of the server the command was ran in, if no arguments was given the current Guild Type will be displayed instead.


#### Usage

    ;set-type
    -  Displays the current guild type.
    ;set-type list
    -  List available guild types.
    ;set-type <type id>
    -  Changes the guild type to the given type.

#### Example

    ;set-type 2
    -  Sets the guild type to VIP+
    ;set-type list
    -  Lists the available guild types.

<a name="SetStatusCommand"></a>
### Set Status Command

Sets the status of the bot instance for all servers the bot is on, if no status is set the bot status will go back to cycling status from the config.


#### Usage

    ;setstatus <game>
    -  Sets the bots playing status to the given game.
    ;setstatus <twitch url>
    -  The URL that the bot should be broadcasting.

#### Example

    ;setstatus with some stuff

<a name="ShutdownCommand"></a>
### Shutdown Command

Schedules a time the bot should be shutdown gracefully.


#### Usage

    ;shutdown now
    -  Shuts down the bot now.
    ;shutdown cancel
    -  Cancels the shutdown process.
    ;shutdown <time>
    -  Schedules a time the bot should be shutdown.


<a name="UpdateCommand"></a>
### Update Command

Schedule a time the bot should be automatically-updated, the bot will shutdown, update itself, and start back up again.
This requires [avaire/watchdog](https://github.com/avaire/watchdog) to work, or that the `--internal-restart` flag was used when starting the bot, without it the bot will just shutdown.


#### Usage

    ;update now
    -  Updates the bot now.
    ;update cancel
    -  Cancels the update process.
    ;update <time>
    -  Schedules a time the bot should be updated.


