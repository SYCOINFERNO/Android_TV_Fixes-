# Android_TV_Fixes
This hold all the tips and quirks I found while I was experimenting with the features of AndroidTV



## *Now first thing first If you want to do any of this you need to have adb or platform tools inorder to do some of these features*


Install platform tools from https://developer.android.com/tools/releases/platform-tools on to your device like a Laptop 
 *  Sheild Optimizer from github https://github.com/bryanroscoe/shield_optimizer
 *  If you dont want to use your laptop then I recommend using atvTools by tvDev
   
Next I would start with what tv you have 
    *  Sony
    *  TCL
    *  etc

Now I like not having any Ads or unessessary content on my landing page for a TV 
So starting with that,

## Sheild Optimizer 
Is application that connect to your tv via wireless debugging and allows you to take control of your TV.

The easiest way to tweek the AndroidTV is running the tweeks option in the app, by uninstalling the unused apps and the system apps that you don't want.

## Scrcpy
This connect to your TV giving you the ability to use the keyboard and mouse as it might be difficult to do everything with just the remote. 

## Launchers
Launchers are what allows you to actually change the way you see the tv's content

I have used a few namly 
  *  Projectivy Launcher
  *  FLauncher
  *  etc
You can do a lot with the free version but you can always help the devs with taking the pro version for more personalization features.

Most launchers have a way to change the home button to the new launcher.

In sheild optimizer you have a way to disable the old launcher and set the new one as the default. Sometimes when you have updated the launcher the launcher might not get changed and causing the TV won't boot to any of the launchers so it might boot loop.

This can be fixed by factory resetting the TV to fix the boot loop, you can look for ways to open the recovery options and factory reset it.


## Remote Settings 
Sometimes after you have changed the Launcher the launcher requires Accessibility  settings for remapping the HOME Button and other thinks for that reason you have to give access. Now, it might not work due to the Accessibility settings turned off so for this reason you have to run the followwing command

1. Use atvTools to connect to adb shell and prompt the following command to retrieve the correct flag:
''' bash
adb shell appops get dev.vodik7.tvquickactions.free
'''
You’ll get a list of flags. You should see APP_AUTO_START(or can be named as AUTO_START): ignore, which explains why the accessibility service automatically turns off after a while or when the TV restarts.

2. Allow the APP_AUTO_START(or can be named as AUTO_START) flag using the command:

adb shell appops set dev.vodik7.tvquickactions.free APP_AUTO_START allow  #(or can be named as AUTO_START)

Voila! This should resolve the problem.






