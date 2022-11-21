# App Publishing in Google Play


![Image of Garage](https://pbs.twimg.com/profile_banners/1473251190611877889/1643650277/1500x500)


# The Complete Guide for Publishing your App in Play Store

## Table Of Content 
- [Pre-Publishing](#PrePublish)
  * [Change Package Name](#Change-Package-Name)
  * [Privacy Policy](#Privacy-Policy)
  * [Adding a Launcher Icon](#Adding-a-Launcher-Icon)
- [Release](#Release)
  * [Signing the app](#Signing-the-app)
  * [Prepare your release](#Prepare-your-release)
  * [Common Errors](#Common-Errors)
- [Resources](#Resources)
  * [Documentation](#Documentation)
  * [Video Links](#Video-Links)



<a name="PrePublish"/>
<a name="Change-Package-Name"/>
<a name="Release"/>
<a name="Common-Errors"/>
<a name="Documentation"/>
<a name="Video-Links"/>
<a name="Privacy-Policy"/>
<a name="Resources"/>
<a name="Signing-the-app"/>
<a name="Adding-a-Launcher-Icon"/>
<a name="Prepare-your-release"/>
<a name="Adding-a-Launcher-Icon"/>
<a name="Adding-a-Launcher-Icon"/>






## Pre-Publishing



### Change Package Name
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


### Privacy Policy

Your mobile app (iOS, Android, Windows, BlackBerry) must have a Privacy Policy if the app collects personal data from users.

**A Privacy Policy for Android Apps is Required by Google Play.**

There are some websites that provides a tamplate for such thing. Click [Here](https://www.termsfeed.com/blog/sample-mobile-app-privacy-policy-template/)

### Adding a Launcher Icon

Here in this [link](https://github.com/fluttercommunity/flutter_launcher_icons) how to add a launcher icon for your app using a **Flutter Launcher Icons** Package


## Release



### Signing the app

Application signing allows developers to identify the author of the application and to update their application without creating complicated interfaces and permissions. Every application that is run on the Android platform must be signed by the developer.

![](https://developer.android.com/static/studio/images/publish/appsigning_googleplayappsigningdiagram_2x.png)

On Android, there are two signing keys:
* **Deployment** : The end-users download the .apk signed with the ‘deployment key’
* **Upload** : An ‘upload key’ is used to authenticate the .aab / .apk uploaded by developers onto the Play Store and is re-signed with the deployment key once in the Play Store. 

#### Step 1: Create an upload key:
There are 2 ways to create an upload key:

* Following the [Android Studio key generation steps](https://developer.android.com/studio/publish/app-signing#sign-apk)
* Running the following at the command line:

On Mac/Linux, use the following command:

```
keytool -genkey -v -keystore ~/upload-keystore.jks -keyalg RSA -keysize 2048 -validity 10000 -alias upload
```
 
On Windows, use the following command:
```
keytool -genkey -v -keystore %userprofile%\upload-keystore.jks -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 -alias upload
```
#### Step 2: Configure signing in gradle
1. Go to Your Project/android/app/build.gradle file.
2. Add the keystore information from your properties file before the android block:

```
   def keystoreProperties = new Properties()
   def keystorePropertiesFile = rootProject.file('key.properties')
   if (keystorePropertiesFile.exists()) {
       keystoreProperties.load(new FileInputStream(keystorePropertiesFile))
   }

   android {
         ...
   }

```
Load the key.properties file into the keystoreProperties object.

3. Find the ```buildTypes``` block and replace it with the following signing configuration info:
```
   signingConfigs {
       release {
           keyAlias keystoreProperties['keyAlias']
           keyPassword keystoreProperties['keyPassword']
           storeFile keystoreProperties['storeFile'] ? file(keystoreProperties['storeFile']) : null
           storePassword keystoreProperties['storePassword']
       }
   }
   buildTypes {
       release {
           signingConfig signingConfigs.release
       }
   }
```

### Prepare your release

#### Step 1: Creating developer account


 * Go to [Google Play Console](https://play.google.com/console/u/0/signup) and create an account for developer .
 
 **Note** : Google Play charges a $25 one-time developer fee.
#### Step 2: Setting the app for release
In this video [here](https://www.youtube.com/watch?v=DNXME6ANmR4&ab_channel=tutorialsEU) , detailed instruction on how to set your app for release. Start watching after 2:29 mins.
 





### Common Errors

#### Error: Your Android App Bundle Is Signed With The Wrong Key. Ensure That Your App Bundle Is Signed With The Correct Signing Key And Try Again.
#### Solution 1:
* Rebuild the project and generate signed apk once again !
#### Solution 2:
* click and upload with new keystore file that created manually.
![photo](https://i.stack.imgur.com/0SVBu.png)



#### Error: App URL not found in Google Play (for internal testers)
![not found](https://i.stack.imgur.com/sG5RF.png)
#### Solution:

1. Open your app → Release → Testing → Internal testing
2. Tap on Testers → Scroll down and you will see How testers join your test at the bottom.

![image](https://i.stack.imgur.com/e12dl.png)

After that testers should accept the inventation, install app from Google Play and check the updates

#### Error: .png failed to read PNG signature: file does not start with PNG signature.
![photo](https://i.stack.imgur.com/S03gn.png)

#### Solution 1:
* In build.gradle
```
aaptOptions {
    cruncherEnabled = false
}
```
* Delete content inside C:\Users\.gradle\caches (or ~/.gradle/caches for Mac and Linux).

* Restart Android Studio

#### Solution 2:
* Add  ``` cruncherEnabled = false ``` in build.gradle

#### Solution 3:
* Convert the image into png rather than just changing the extension.

## Resources


### Documentation


* #### [Build and release an Android app](https://docs.flutter.dev/deployment/android)


### Video Links


* #### [Change Package Name](https://www.youtube.com/watch?v=qo-iCbPAi5k&ab_channel=CodeProf)


* #### [Publishing the Android Version of the Flutter App to the Play Store](https://www.youtube.com/watch?v=mUpF8R6Nfcw&ab_channel=RomanJustCodes)

* #### [Flutter: Adding app launcher icons to your project](https://www.youtube.com/watch?v=RjNAxwcP3Tc&ab_channel=MarkO%27Sullivan)






