# Linux Guide

- [Prerequisites](#prerequisites)
    - [Linux Server](#server)
    - [Software](#software)
- [Installing Requirements](#install-requirements)
    - [Java 9](#install-java)
    - [Gradle - Build](#install-gradle)
    - [Git - Source Control](#install-git)
- [MySQL](#install-mysql)
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

Start by logging into your server via your SSH client.

<a name="install-java"></a>
### Installing Java - Oracle JVM

We'll be using Java 9 to run Ava, if you don't already have Java installed, you can install it with the following commands.

    sudo apt install oracle-java9-installer

If your server doesn't have the Oracle repositories saved you can try using updating the repositories and re-attempting to install Java using the command below.

    sudo add-apt-repository ppa:webupd8team/java
    sudo apt update

<a name="install-gradle"></a>
### Installing Gradle

To install Gradle 4.8 and be able to build your .jar file you'll need to install SDKMAN! first with the following:

    curl -s "https://get.sdkman.io" | bash
    source "$HOME/.sdkman/bin/sdkman-init.sh"

Then Gradle itself:

    sdk install gradle 4.8

<a name="install-git"></a>
### Installing Git (Optional)

Next we'll install Git to be able to download and update Ava, git will also be used later on if you want to update Ava to the latest version.

Start off by checking if git is already installed, some services that offers Linux servers comes with Git pre-installed, you can check if git is installed by running:

    git --version

If the command is not found you can install git by running

    sudo apt install git

<a name="install-mysql"></a>
## Installing MySQL

We need a Database for AvaIre to work from.
First we need to download MySQL, doing the following:

    sudo apt-get install mysql-server

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

    git clone https://github.com/avaire/avaire.git .

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
