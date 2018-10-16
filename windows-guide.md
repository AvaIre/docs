# Windows Guide

- [Prerequisites](#prerequisites)
    - [Windows System](#windows)
    - [Software](#software)
- [Installing Requirements](#install-requirements)
    - [Java & Gradle](#install-java)
    - [Git - Source Control](#install-git)
- [Installing Ava](#install-ava)
- [Configuration of Ava](#configuration)
- [Running the bot](#running-the-bot)
- [System Commands](#system-commands)
    - [Application Restart](#commands-restart)
    - [Application Shutdown](#commands-shutdown)
    - [Application Update](#commands-update)
    - [Global Blacklist](#commands-blacklist)
    - [Set Guild Type](#commands-set-type)
    - [Evaluate Code](#commands-eval)
    - [Reload Configuration](#commands-reload)
    - [Set Bot Status](#commands-status)
    - [Lavalink](#commands-lavalink)

<a name="prerequisites"></a>
## Prerequisites

<a name="windows"></a>
#### Windows

 * 1GB of ram or more
 * Windows 7 and higher
 * Administrator access to the computer

<a name="software"></a>
#### Software

 * [Java & Gradle](#install-java)
 * [Git](#install-git) &nbsp; (Optional)
 * MySQL Database &nbsp; ([XAMPP](https://www.apachefriends.org/) is recommended for beginners)
 * A code editor, i.e. [Notepad++](https://notepad-plus-plus.org/) or [Atom](https://atom.io/) or [Sublime Text](https://www.sublimetext.com/)

<a name="install-requirements"></a>
## Installing Requirements

> {tip} A number of steps require administrative access to finish installing both Git and Java correctly, because of this it is recommended that you're logged in as an administrator to not have to type the admin password a whole bunch of times.

<a name="install-java"></a>
### Installing Java & Gradle

AvaIre is a Java application, because of this we'll need to install Java to run Ava, if you don't already have Java installed, head over to the [Oracle Java download page](http://www.oracle.com/technetwork/java/javase/downloads/index.html) to get started, then select the latest Java Platform (JDK), accept Oracles license, and download the windows .exe file, once Java has been installed you may need to add Java to your windows system path variable, check out the "[how to set java home on windows 10](https://www.mkyong.com/java/how-to-set-java_home-on-windows-10/)" guide by [mkyong](https://twitter.com/mkyong) for how to get started with doing that.

If you want to run the cutting edge of Ava you can download the [nightly build](https://avairebot.com/nightly-build.zip) from avairebot.com, the zip file gets updated once every 24 at midnight CEST, you can also download a stable version of the bot from the [github releases](https://github.com/avaire/avaire/releases), or you can use Gradle to build your own jar file, gradle is used by Ava to compile all the source code into a binary file that the computer can run, you can get gradle from [Gradles install page](https://gradle.org/install/).

If you choose to use a github release or the nightly build, you can skip installing Git and jump right into setting up the bot.

<a name="install-git"></a>
### Installing Git (Optional)

If you don't want to run the cutting edge versions of Ava you can skip this step.

While running the cutting edge version of Ava it is recommended that you install git since using it makes it a whole lot easier to keep Ava up to date.

If you don't already have git installed you can get started by going to the [git-scm download page](https://git-scm.com/downloads) and download the Windows installer.

 > {tip} **Note:** The installation process for git is very particular, if you don't install it like described below you'll most likely run into issues down the road.

Once downloaded, run the installer, read the license and continue, you can leave the component selection with its default settings, jue make sure that the **Windows Explorer Intergration** is ticked off.

<img src="https://avairebot.com/assets/img/guides/git-setup-1.png" alt="Git Setup - Components">

> The next few steps a really particular, make sure you follow the steps as described below so you don't run into a roadblock later on.

<img src="https://avairebot.com/assets/img/guides/git-setup-2.png" alt="Git Setup - Path">
<img src="https://avairebot.com/assets/img/guides/git-setup-3.png" alt="Git Setup - SHH">
<img src="https://avairebot.com/assets/img/guides/git-setup-4.png" alt="Git Setup - HTTPS Transport">
<img src="https://avairebot.com/assets/img/guides/git-setup-5.png" alt="Git Setup - Line Ending">
<img src="https://avairebot.com/assets/img/guides/git-setup-6.png" alt="Git Setup - Terminal">

From here on just continue with the installation process until Git is installed.

<a name="install-ava"></a>
## Installing Ava

Next, we'll retrieve the AvaIre GitHub repository, we will be using Git to install Ava so it will be easier to update later on, if you skipped install git you can find the [latest release](https://github.com/avaire/avaire/releases) of Ava on github and skip right to the setup process.

You'd want to figure out where you want the bot to be downloaded. Something simple where you can find it is good, AKA not in the system internals (Possibly some other drive, though NOT A FLASH DRIVE) or optionally your Desktop could be fine.

When you've found the location of your choice, hit `Shift+Right click` and select **Git Bash here**. This will open the Git Bash console. Type the following command into Git Bash:

    git clone https://github.com/avaire/avaire.git
    cd avaire

Let it clone the Git repository. When it's done, you should have the following output.

<img src="https://avairebot.com/assets/img/guides/ava-setup.png" alt="Git Setup">

You have now successfully cloned the AvaIre Git repository, next we'll need to build the jar file from the source code, we can do this by utilizing gradle which we just installed.

    gradle build

If the build finishes with no errors you should be good to go! You can find the generated binary file at `build/libs/AvaIre.jar`.

<a name="configuration"></a>
## Configuration of Ava

Next we'll need to configure Ava so the bot can connect and communicate with users, to generate the `config.yml` file we'll just need to run Ava once, we can do this by running:

    java -jar AvaIre.jar
    
You can now open the new `config.yml` file in  Notepad++ or any other code editor. **Do not edit it with Windows Notepad, that will be a mess.**

Next we'll need to setup a database the Ava can use, Ava requires a database to store things like custom playlists, aliases, channel and server data, and a lot of other things, Ava currently only has support for MySQL databases, with SQLite and other types coming in the future.


Now that the database is in order you'll need to put your Discord Bot Application token in the `bot.token` property, you can find your bot token under your Discord Application dashboard, if you don't have a Discord bot application setup you can create one easily by following these steps.

 1. Start by heading to [discordapp.com/developers/applications](https://discordapp.com/developers/applications/me), once you're there you can create a new application, you can name it whatever you want and give it a fancy picture and description if you want to, once you're done click **Create App**.
 2. Your application should now have been created, next click on the **Create a Bot User** button, this will convert the application to a bot user application.
 3. Now that you have a user bot application you can get your bot token under the **App Bot User** section.

> {tip} If you want other people to be able to invite the bot you must check the **Public Bot** options under your **App Bot User** application settings, if you don't do that you will be the only one that can invite the bot to servers.

On your bot application dashboard you'll also be able to find your bot client id, we'll need that later to invite the bot so keep onto it.

If you want a more in-detail guide and walkover for the [configuration](/docs/{{version}}/configuration) file you can checkout the [Configuration](/docs/{{version}}/configuration) page, all the settings and options are covered in more detail on that page with guides on how to setup each option.

<a name="running-the-bot"></a>
## Running the bot

Congratulations, your AvaIre instance should now be ready to launch!

To start the bot, simply just run the jar file again after editing it with your bot and database details.

    java -jar AvaIre.jar

If the bot runs without any errors, you have had success so far!

> {tip} Windows may start the Java VM without UTF-8 encoding(Which can cause some language files to send messages with missing characters), or/and doesn't parse colors correctly(Which can make the console almost un-readable), you can fix this by using the `-Dfile.encoding=UTF-8` and `--no-colors` flag respectively:<br>```java -Dfile.encoding=UTF-8 -jar AvaIre.jar --no-colors```

Now you'll need to invite your bot to your server so you can actually use it, take your bots client id from earlier and pop it into a URL like this without the less than and greater than symbols.

    https://discordapp.com/oauth2/authorize?&client_id=<client id>&scope=bot

Just replace the `<client id>` with your actually bot application id, if you don't have your client id you can find it on the [discordapp.com/developers/applications](https://discordapp.com/developers/applications/me) page, just click on your application, the client ID is at the very top under the **App Details** section.

Go to the URL in a web browser, select your server and ht `Authorize`, your bot should now be on your server.

You can test simple functionality by running the ping command in a text channel that the bot can see. If it answers "Pong!", then congratulations, you have successfully set up AvaIre!

Remember to keep the command window open, otherwise the bot will stop running! When you want to stop it, just close the command window.
And that's it! You are now ready to start using your very own AvaIre instance!
Keep in mind, if you have further questions or need help, we're around over at our official server, [AvaIre Central](https://discord.gg/gt2FWER)!

On the behalf of the AvaIre team, we hope you enjoy your bot!

<a name="system-commands"></a>
## System Commands

> System commands can only be seen and run by bot administrators, ie, people who have their user ID in the bot admins field in the config of the bot.

All system commands uses a semicolon(;) as their prefix by default. 

| Command           | Short Description      |
| ----------------- |:---------------------- |
| [;restart <when\>](#commands-restart)  | Restarts the application gracefully  |
| [;shutdown <when\>](#commands-shutdown)  | Shuts down the application gracefully  |
| [;update <when\>](#commands-update)  | Updates the bot to the latest version  |
| [;blacklist <option\>](#commands-blacklist)  | Adds, Removes and Lists servers/users on the global blacklist |
| [;set-type <type\>](#commands-set-type)  | Sets the Guild Type of the server the command was ran in |
| [;eval <code\>](#commands-eval)  | Evaluate and executes raw code and returns the result  |
| [;reload](#commands-reload)  | Reloads the main config and all plugin configs  |
| [;status](#commands-status)  | Set the playing status of the bot   |
| [;lavalink <options\>](#commands-lavalink)  | Add, remove, and manage Lavalink nodes   |

<a name="commands-restart"></a>
### Application Restart

Schedule a time the bot should be automatically-restarted, the bot will shutdown, then start back up again.
This requires [Watchdog](https://github.com/avaire/watchdog) to work, without it the bot will just shutdown.

#### Usage

    ;restart now - Restarts the bot now
    ;restart cancel - Cancels the restart process
    ;restart <time> - Schedules a time the bot should be restarted

<a name="commands-shutdown"></a>
### Application Shutdown

Schedules a time the bot should be shutdown gracefully.

#### Usage

    ;shutdown now - Shuts down the bot now.
    ;shutdown cancel - Cancels the shutdown process.
    ;shutdown <time> - Schedules a time the bot should be shutdown.

<a name="commands-update"></a>
### Application Update

Schedule a time the bot should be automatically-updated, the bot will shutdown, update itself to the latest version from github, and start back up again.
This requires [Watchdog](https://github.com/avaire/watchdog) to work, without it the bot will just shutdown.

#### Usage

    ;update now - Updates the bot now.
    ;update cancel - Cancels the update process.
    ;update <time> - Schedules a time the bot should be updated.

<a name="commands-blacklist"></a>
### Global Blacklist

Add, Remove, and list users and servers on the blacklist. Users and servers on the blacklist will be ignored by Ava, regardless of their permissions, or roles on any server, 

#### Usage

    ;blacklist list - Lists users and servers on the blacklist.
    ;blacklist remove <id> - Removes the entry from the blacklist.
    ;blacklist add <type> <id> <reason> - Add the ID to the blacklist.

<a name="commands-set-type"></a>
### Set Guild Type

Sets the Guild Type of the server the command was ran in, if no arguments was given the current Guild Type will be displayed instead.

> Ava has an internal ranking system for guilds/servers, different ranks can give servers different limits for commands like [playlists](/docs/{{version}}/commands#PlaylistCommand) and [aliases](/docs/{{version}}/commands#AliasCommand), 

#### Usage

    ;set-type - Displays the current guild type.
    ;set-type list - List available guild types.
    ;set-type <type id> - Changes the guild type to the given type.

<a name="commands-eval"></a>
### Evaluate Code

Runs the given piece of code as the bot.

> This command is really dangerous to use if you don't know what you're doing! Use it at your own risk!

#### Usage

    ;eval <code> - Runs the given code as the bot.

<a name="commands-reload"></a>
### Reload Configuration

Reloads the main `config.yml` configuration file, and all the configs for enabled plugins.

#### Usage

    ;reload - Reloads all the configs.

<a name="commands-status"></a>
### Set Bot Status

Sets the status of the bot instance for all servers the bot is on, if no status is set the bot status will go back to cycling status from the config.

#### Usage

    ;setstatus - Goes back to cycling status from the config.
    ;setstatus <game> - Sets the bots playing status to the given game.
    ;setstatus <twitch url> - The URL that the bot should be broadcasting.

<a name="commands-lavalink"></a>
### Lavalink

This command can be used to list the status of Lavalink nodes, adding, and removing nodes on the fly during runtime.

#### Usage

    ;lavalink list - List all Lavalink nodes
    ;lavalink show <node> - Shows in-depth information about the node
    ;lavalink add <name> <url> <pass> - Adds the node to Lavalink
    ;lavalink remove <name> - Removes the node from Lavalink