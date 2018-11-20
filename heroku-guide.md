# Heroku Guide

- [Hosting from source](#hosting-from-source)
  - [Prerequisites](#hosting-from-source-prerequisites)
    - [Software](#hosting-from-source-software)
  - [AvaIre](#hosting-from-source-avaire)
    - [Deploy method](#hosting-from-source-avaire-deploy)
      - [Small note](#hosting-from-source-avaire-deploy-note)
  - [Watchdog](#hosting-from-source-watchdog)
    - [Deploy method](#hosting-from-source-watchdog-deploy)
      - [Small note](#hosting-from-source-watchdog-deploy-note)
- [Hosting from a jar](#hosting-from-a-jar)
  - [Prerequisites](#hosting-from-a-jar-prerequisites)
    - [Software](#hosting-from-a-jar-software)
  - [AvaIre](#hosting-from-a-jar-avaire)
  - [Watchdog](#hosting-from-a-jar-watchdog)
- [Troubleshooting](#trouble-shooting)

<a name="hosting-from-source"></a>
## Hosting from source
> {tip} When you choose to host from source. It's recommended to get a GitHub account, as you can use this to fork the repo, to keep AvaIre up to date more easily. 

<a name="hosting-from-source-prerequisites"></a>
### Prerequisites

> {tip} This guide assumes you already have a basic understanding of how Heroku works, and how to fill in the config.yml file/environment variables.
> 
> Also it's required that you have a Heroku account. 
> 
> It's however not required to have a credit card linked to it, but it's recommended so you have enough hours to keep AvaIre working throughout the month.

<a name="hosting-from-source-software"></a>
#### Software
 * No software is actually needed. Everything is done through the browser.

<a name="hosting-from-source-avaire"></a>
### AvaIre
When, using AvaIre from source, you are able to use the deploy button, and still have full control over the source. Allowing you to make your own changes.
However, updating is slightly more complicated, as you need to make sure to get the changes to Heroku. There is a solution to this where we get back to in a bit.

Navigate to [AvaIre's repo](https://github.com/avaire/avaire) and click on the deploy button.
Fill in the config environment variables. The environment variables: `AVA_DATABASE_DATABASE`, `AVA_DATABASE_HOSTNAME`, `AVA_DATABASE_USERNAME` and `AVA_DATABASE_PASSWORD` will be changed later.

After your done filling in the environment variables, you can click on deploy. After your AvaIre is deployed on Heroku, click on Manage App.

Now click on: JawsDB MySQL Kitefin Shared. And copy the following values, to the corresponding environment variables.

You can find the variables again, by clicking on settings, followed by clicking on Reveal Config Vars. 
Click on the pen to edit the value of a config variable.

| Property     | Value      | Config Vars |
| :------------| :----------| :---------- |
| Host | k3xio06abq.cbetxkdy.us-east-1.rds.amazonaws.com | AVA_DATABASE_HOSTNAME |
| Username | ddodhx8vm1ykdkcg  | AVA_DATABASE_USERNAME |
| Password | f8iu1aol63w91qsa  | AVA_DATABASE_PASSWORD |
| Port | 3306 | Not Needed! |
| Database   | irxi1s355bm3o0vt | AVA_DATABASE_DATABASE |

<br>
So, for example `AVA_DATABASE_HOSTNAME`  `HOSTNAME` will be changed to: `AVA_DATABASE_HOSTNAME` `irxi1s355bm3o0vt` on the settings page.

Now you've successfully configured AvaIre on Heroku. You can see her logs by click on: `More` on the top right, followed by clicking on `View logs`. If you want to turn off AvaIre, click on `Resources`, followed by clicking on the pen, clicking on the toggle, and clicking on `confirm`.

<a name="hosting-from-source-avaire-deploy"></a>
#### Deploy method
> {tip} This part assumes you have a GitHub account, as well as a _working_ AvaIre hosted on Heroku.

To keep AvaIre up-to-date, after following the above method. Go to [AvaIre's main repo](https://github.com/avaire/avaire) and click on fork.

Now go back to Heroku and click on `Deploy`. Click on `GitHub Connect to GitHub`, and login if necessary. Click on `Search` and connect the repo that you just forked.

Make sure the right branch is chosen (master in this case). You can click on `Enable Automatic Deploys`.

To make sure everything is still working, click on `Deploy Branch` to start deploying from your own fork.

Once deployment is successful, go to https://backstroke.co/ and login with GitHub.

Click on `Create Link` and give your link a nice name.

For the Upstream fill in: `avaire/avaire`, and choose the master branch.

Choose `One fork`, and fill in your username with the forked repo. For example: Macley-Kun/avaire, with the branch master.

Click on Save. You can click on Resync to manually start synching the upstream repo, with your fork. Any commits that are merged into the upstream, will come as a pull request from backstrokebot to your fork.
You only have to manually merge the pull by going to your fork from time to time. Click on Merge pull request, followed by clicking on `Confirm merge`.

In less then a minute, Heroku will pick up the changes and re-deploy.

<a name="hosting-from-source-avaire-deploy-note"></a>
#### Small note
If you changed some files in your fork, it's possible that you will have a merge conflict. You have to manually fix this yourself by following the tips/FAQ GitHub gives you on that pull and merging it manually through the command line or GitHub desktop app.

<a name="hosting-from-source-watchdog"></a>
### Watchdog
When using Watchdog from source, you are able to use the deploy button, and still have full control over the source of Watchdog. Allowing you to make your own changes. You are however not able to change the source of AvaIre.

However, updating is slightly more complicated, as you need to make sure to get the changes to Heroku. There is a solution to this where we get back to in a bit.
As Watchdog downloads AvaIre.jar after it detects it's missing. This method will always give you the latest versions, without any hassle. Watchdog itself however still would lack updating itself.

Navigate to [Watchdog's main repo](https://github.com/avaire/watchdog) and click on `the deploy button`.
Fill in the config environment variables, the environment variables like: `AVA_DATABASE_DATABASE`, `AVA_DATABASE_HOSTNAME`, `AVA_DATABASE_USERNAME` and `AVA_DATABASE_PASSWORD` are later going to be changed.

After your done filling in the environment variables, you can click on `deploy`. After you Watchdog is deployed on Heroku, click on `Manage App`. Now click on: `JawsDB MySQL Kitefin Shared`. And copy the following values, to the corresponding environment variables.

You can find the variables again, by clicking on settings, followed by clicking on Reveal Config Vars. 
Click on the pen to edit the value of a config variable.

| Property     | Value      | Config Vars |
| :------------| :----------| :---------- |
| Host |    k3xio06abq.cbetxkdy.us-east-1.rds.amazonaws.com | AVA_DATABASE_HOSTNAME |
| Username | ddodhx8vm1ykdkcg  | AVA_DATABASE_USERNAME |
| Password | f8iu1aol63w91qsa  | AVA_DATABASE_PASSWORD |
| Port | 3306 | Not Needed! |
| Database   | irxi1s355bm3o0vt | AVA_DATABASE_DATABASE |

<br>
So, for example: `AVA_DATABASE_HOSTNAME` `HOSTNAME` will be changed to: `AVA_DATABASE_HOSTNAME` `irxi1s355bm3o0vt` on the settings page.

Now you've successfully configured Watchdog on Heroku. You can see her logs by click on: `More` on the top right, followed by clicking on `View logs`.

If you want to turn off Watchdog, click on `Resources`, followed by clicking on the `pen`, clicking on the button, and lastly click on `confirm`.

<a name="hosting-from-source-watchdog-deploy"></a>
#### Deploy method
> {tip} This part assumes you have a GitHub account, as well as a _working_ AvaIre hosted on Heroku.

To keep Watchdog up-to-date, after following the above method, go to [Watchdog's main repo](https://github.com/avaire/watchdog) and click on `Fork`.

Now go back to Heroku and click on `Deploy`. Click on `GitHub Connect to GitHub`, and login if necessary. Click on `Search` and connect the repo that you just forked.

Make sure the right branch is chosen (master in this case). You can click on `Enable Automatic Deploys`.

To make sure everything is still working, click on `Deploy Branch`, to start deploying from your own fork.

Once deployment is successful, go to https://backstroke.co/ and login with GitHub.

Click on `Create Link` and give your link a nice name.

For the Upstream fill in: `avaire/watchdog`, and choose the master branch.

Choose One fork, and fill in your username with the forked repo. For example: Macley-Kun/watchdog, with the branch master.

Click on Save. You can click on Resync to manually start synching the upstream repo, with your fork. Any commits that are merged into the upstream, will come as a pull request from backstrokebot to your fork.
You only have to merge the pull by going to your fork from time to time. Click on `Merge pull request`, followed by clicking on `Confirm merge`.

In less then a minute, Heroku will pick up the changes and re-deploy.

<a name="hosting-from-source-watchdog-deploy-note"></a>
#### Small note
If you changed some files in your fork, it's possible that you will have a merge conflict. You have to manually fix this yourself by following the tips/FAQ GitHub gives you on that pull and merging it manually through the command line or GitHub desktop app.

<a name="hosting-from-a-jar"></a>
## Hosting from a jar

<a name="hosting-from-a-jar-prerequisites"></a>
### Prerequisites

> {tip} This guide assumes you already have a basic understanding of how Heroku works, and how to fill in the config.yml file/environment variables.
>
> It's also required that you have a Heroku account.
> 
> It's however not required to have a credit card linked to it, but it's recommended so you have enough hours to keep AvaIre working throughout the month.

<a name="hosting-from-a-jar-software"></a>
#### Software

 * [Git](https://git-scm.com/downloads)
 * [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli#download-and-install)

> {tip} Make sure to [set a username in git](https://help.github.com/articles/setting-your-username-in-git/), as well as to login [into the Heroku CLI tool](https://devcenter.heroku.com/articles/heroku-cli#getting-started).

<a name="hosting-from-a-jar-avaire"></a>
### AvaIre

First, download the [AvaIre.jar](https://avairebot.com/nightly-build.jar), the [config.yml](https://raw.githubusercontent.com/avaire/avaire/master/src/main/resources/config.yml) and the [Procfile](https://raw.githubusercontent.com/avaire/avaire/master/Procfile).
Put these all in a folder, then open within this folder git bash/commandprompt. Do the following to create a heroku application, set the buildpacks, etc.
```
git init
heroku apps:create NAMEHEROKUAPP --region eu
heroku addons:create jawsdb:kitefin
heroku buildpacks:set heroku/jvm
```
Replace NAMEHEROKUAPP with a name you like, lowercase only. Optionally you change the region to `us` if that's closer to your servers.

You can ether fill in the config.yml file, or set the env variables yourself by using:
`heroku config:set AVA_NAMEVARIABLE=VALUEVARIABLE`

So for setting the token, you would type in:
`heroku config:set AVA_DISCORD_TOKEN=myt0ken`

Here is [the list of all the environment variables AvaIre uses](https://github.com/avaire/avaire/blob/master/app.json).

To push your changes, do the following in the same terminal:
```
git add .
git commit -am "First commit!"
git push heroku master
```

Whenever you change some of the files, you only have to repeat the above part.

You can start AvaIre by doing:
`heroku ps:scale worker=1`

And stop her by doing:
`heroku ps:scale worker=0`

To tail the logs trough the terminal you can type in:
`heroku logs --tail`

<a name="hosting-from-a-jar-watchdog"></a>
### Watchdog

First, download the [Watchdog.jar](https://github.com/avaire/watchdog/releases), the [config.yml](https://raw.githubusercontent.com/avaire/avaire/master/src/main/resources/config.yml) and the [Procfile](https://raw.githubusercontent.com/avaire/watchdog/master/Procfile).
Put these all in a folder, then open within this folder git bash/commandprompt. Do the following to create a heroku application, set the buildpacks, etc.
```
git init
heroku apps:create NAMEHEROKUAPP --region eu
heroku addons:create jawsdb:kitefin
heroku buildpacks:set heroku/jvm
```
Replace NAMEHEROKUAPP with a name you like, lowercase only. Optionally you change the region to `us` if that's closer to your servers.

You can ether fill in the config.yml file, or set the env variables yourself by using:
`heroku config:set AVA_NAMEVARIABLE=VALUEVARIABLE`

So for setting the token, you would type in:
`heroku config:set AVA_DISCORD_TOKEN=myt0ken`

Here is [the list of all the environment variables AvaIre uses](https://github.com/avaire/avaire/blob/master/app.json).

To push your changes, do the following in the same terminal:
```
git add .
git commit -am "First commit!"
git push heroku master
```

Whenever you change some of the files, you only have to repeat the above part.

You can start Watchdog by doing:
`heroku ps:scale worker=1`

And stop Watchdog by doing:
`heroku ps:scale worker=0`

To tail the logs trough the terminal you can type in:
`heroku logs --tail`

<a name="trouble-shooting"></a>
## Troubleshooting
 * Make sure you are logged in. You can log in with the `heroku login` command.
 * You can find your logs by typing: heroku logs --tail. It's recommended to start logging before pushing/start your app.
 * You can run into problems if you didn't install all the requirements, double check your configs or check if skipped a command.

There are also a few known issues when hosting through Heroku, you can find the list in [this issue](https://github.com/avaire/avaire/issues/56).
