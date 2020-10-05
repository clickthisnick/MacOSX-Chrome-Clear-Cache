# Information

This repository contains code that allows a person to programatically (Without human intervention) clear their Chrome browser cache.

I like to clear the Chrome browser cache periodically so that when I type into the Chrome omnibar (address bar), my recently visited sites do not pop up, thus less temptation to deviate from my current computer task and click to a site I've visited before.

# Usage

## From the application

`chromeClearCache.app` is an AppleScript application. You can double click it to execute.

## Once on computer login

Go to `System Preferences -> Users & Groups -> Login Items` and then find the path to the `chromeClearCache.app`. 

This means the next time you login to your computer, the `chromeClearCache.app` will run automatically

In order for the application to send a keystroke, you would have to allow accessibility rights.
`System Preferences -> Security & Privacy -> Privacy (tab) -> Accessibility (On the left menu)` and check `chromeClearCache.app`

Without the keystroke sending, the chrome page would still open up, you would just have to click continue yourself.

Remember, you can always Export your own Applescript application from the `chromeClearCache.scpt` source code aswell.

## Via a schedule (cron)

Mac OSX has the ability to run scripts on a schedule. If you use the Finder (Cmd + Space) and type in Terminal and hit enter, you will have a command prompt open up. From here you can enter in the following without quote `crontab -e`. crontab allows us to execute commands on a certain schedule. 

For example let's take an extreme example and say you wanted to clear your Chrome cache every 5 minutes. On that `crontab -e` screen you could enter the following:
`*/5 * * * * osascript pathTo/chromeClearCache.scpt`

Of course, every 5 minutes is a bit too much, thankfully, there is a great site to help figure out the correct scheduling command [here](https://crontab.guru/)

# Files Explained

## chromeClearCache.app

This is the application that can be executed to clear your Chrome browser cache.

## chromeClearCache.scpt

This is the AppleScript code. It it does the same thing as the application, but is not exported as an application.

You can run on the terminal prompt with (Change `pathTo` to the computer file path to the application file) - `osascript pathTo/chromeClearCache.app`