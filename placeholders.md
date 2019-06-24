# String Placeholders

- [User Placeholders](#user-placeholders)
    - [User](#user)
    - [User ID](#userid)
    - [Username](#username)
    - [User Discriminator](#userdisc)
- [Channel Placeholders](#channel-placeholders)
    - [Channel](#channel)
    - [Channel ID](#channelid)
    - [Channel Name](#channelname)
- [Server Placeholders](#server-placeholders)
    - [Server Name](#servername)
    - [Server ID](#serverid)
- [Other Types](#other-types-placeholders)
    - [New line](#new-line)

<a name="introduction"></a>
## Introduction

String placeholders are variables you can use in option-based commmands like the [!welcomemessage](/docs/{{version}}/commands#WelcomeMessageCommand) command, the placeholders gives you a wider range of customizability, allowing you to show information dynamically.

All placeholders starts and ends with a percentage sign (%), and wraps the variable name, in combination with each other it would look like `%username%` if you wanted to get the users username.

In all of the following examples the **[AvaIre Central](https://avairebot.com/support)** server will be used as the server example, and the user that will be used is **JohnDoe**#**2854**.

<a name="user-placeholders"></a>
## User Placeholders

<a name="user"></a>
### %user%

Tags the user that triggered the the message.

#### Example

    @JohnDoe#2854

<a name="userid"></a>
### %userid%

Gets the id of the user that triggered the the message.

#### Example

    88739639380172800

<a name="username"></a>
### %username%

Gets the username of the user that triggered the the message.

#### Example

    JohnDoe

<a name="userdisc"></a>
### %userdisc%

Gets the discriminator of the user that triggered the the message.

#### Example

    2854

<a name="channel-placeholders"></a>
## Channel Placeholders

<a name="channel"></a>
### %channel%

Tags the channel that triggered the the message.

#### Example

    #general

<a name="channelid"></a>
### %channelid%

Gets the id of the channel that triggered the the message.

#### Example

    299205123673030658

<a name="channelname"></a>
### %channelname%

Gets the name of the channel that triggered the the message.

#### Example

    general

<a name="server-placeholders"></a>
## Server Placeholders

<a name="servername"></a>
### %servername%

Gets the name of the server the message was triggered in.

#### Example

    AvaIre Central

<a name="serverid"></a>
### %serverid%

Gets the id of the server the message was triggered in.

#### Example

    284083636368834561

<a name="other-types-placeholders"></a>
## Other Types of Placeholders

<a name="new-line"></a>
### %br%

Creates a new line for the message, br will "break the row" of the current message, creating a new line.

#### Example

    This is a
    test message.
