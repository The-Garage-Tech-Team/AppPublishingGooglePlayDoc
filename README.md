# App Publishing in Google Play


![Image of Garage](https://pbs.twimg.com/profile_banners/1473251190611877889/1643650277/1500x500)


# The Complete Guide for Publishing your App in Play Store

## Table Of Content 
- [Pre-Publishing](#PrePublish)
  * [Change Package Name](#Change-Package-Name)
  * [Privacy Policy](#Privacy-Policy)
- [Release & Publishing](#Release-&-Publishing)
  * [Git Init](#Git-Init)
  * [Common Errors](#Common-Errors)
- [Resources](#Resources)
  * [Documentation](#Documentation)
  * [Video Links](#Video-Links)



<a name="PrePublish"/>
<a name="Change-Package-Name"/>
<a name="Release-&-Publishing"/>
<a name="Common-Errors"/>
<a name="Documentation"/>
<a name="Video-Links"/>
<a name="Privacy-Policy"/>
<a name="Resources"/>
<a name="Git-Push"/>
<a name="Git-Pull"/>





## Pre-Publishing



## Change Package Name
You need to use a different **package name** because "com.example" is restricted
Make sure you choose a package name that is suitable over the life of your application. You cannot change the package name after you distribute your application to users.

1. You need to set the package name using the applicationId in your project's build.gradle file:

```
defaultConfig {
        applicationId "com.example.yourProject"
  
    }
```
Change it into something unique for example:
```
defaultConfig {
        applicationId "com.developerName.yourProject"
  
    }
```
2. Then you can right-click on the package in your main/java folder and select Refactor > Rename. Select Refactor Package and type the new one you just used in applicationId.

3. You'll need to re-sync Gradle and rebuild the project after this, of course. :)


## Privacy Policy

Your mobile app (iOS, Android, Windows, BlackBerry) must have a Privacy Policy if the app collects personal data from users.

There are some websites that provides a tamplate for such thing. Click [Here](https://www.termsfeed.com/blog/sample-mobile-app-privacy-policy-template/)

## Adding a Launcher Icon

Here in this [link](https://github.com/fluttercommunity/flutter_launcher_icons) how to add a launcher icon for your app using a **Flutter Launcher Icons** Package


## Release & Publishing



### Common Errors

The `git status`command  lets you see which changes have been staged, which haven’t, and which files aren’t being tracked by Git. Status output does not show you any information regarding the committed project history. For this, you need to use `git log`.



## Resources


## Documentation


* [Build and release an Android app](https://docs.flutter.dev/deployment/android)


## Video Links


* #### [Change Package Name](https://www.youtube.com/watch?v=qo-iCbPAi5k&ab_channel=CodeProf)


* #### [Publishing the Android Version of the Flutter App to the Play Store](https://www.youtube.com/watch?v=mUpF8R6Nfcw&ab_channel=RomanJustCodes)

* #### [Flutter: Adding app launcher icons to your project](https://www.youtube.com/watch?v=RjNAxwcP3Tc&ab_channel=MarkO%27Sullivan)






