# Lovelace | SDK / API level 33 (Android 13 - Tiramisu)
Lovelace is a compiled assets for building both android and ios hybrid mobile app using Apache Cordova partnered with Lonica CSS Framework for the UI. It was named after Ada Lovelace the first computer programmer.

<img src="https://firebasestorage.googleapis.com/v0/b/lonica.appspot.com/o/img%2Fada-lovelace.jpg?alt=media&token=7232e9ed-4557-41b9-9ba6-ab954dc66893" style="max-width:100%;" width="325">

### https://cordova.apache.org (Apache Cordova)

### STEP 1: Make sure to have all of these installed on your machine.

```sh
-------------------------------------
1. https://nodejs.org/en/
2. https://git-scm.com/downloads
3. https://www.oracle.com/ph/java/technologies/javase/javase8-archive-downloads.html | Select Java 8 or 11
4. https://developer.android.com/studio | Select SDK Build Tools 33.0.2 / API level 33 (Android 13 - Tiramisu)
5. https://gradle.org/ | Select the latest version
5. Configure Environment Variables
   Watch the installation process bit.ly/3JX1aXa
```

### STEP 2: Apache Cordova Framework Installation via NPM

```sh
npm i -g cordova@12.0.0
```

### STEP 3: Check if cordova requirements successfully installed by running the command below:

```sh
(Run this command inside the "Lovelace Folder/Directory")

cordova requirements android --verbose 

(You should be seeing a message something like this)

Java JDK: installed 11.0.20
Android SDK: installed true
Android target: installed android-33
Gradle: installed C:\Gradle\gradle-8.3\bin\gradle.BAT
```

### STEP 4: Creating a Project

```sh
cordova create Facebook com.facebook.katana Facebook 

(Replace facebook with your own App Name, and for the katana that refers to your own system-level codename, put your own code/company name.)
```

### STEP 5: Adding/Removing Platform

```sh
- cordova platform add android@12.0.1

- cordova platform remove android@12.0.1
```

### Building your app

```sh
cordova run, build or emulate

cordova build android
```

### Sample Cordova Plugins:

```sh
cordova plugin add PLUGIN_NAME (Adding a specific plugin)
cordova plugin remove PLUGIN_NAME (Removing a specific plugin)

cordova plugin add cordova-plugin-statusbar
cordova plugin add cordova-plugin-splashscreen
cordova plugin add cordova-plugin-whitelist
cordova plugin add cordova-plugin-dialogs
cordova plugin add cordova-plugin-inappbrowser
cordova plugin add cordova-plugin-network-information
cordova plugin add cordova-plugin-x-socialsharing
cordova plugin add cordova-plugin-battery-status
cordova plugin add cordova-plugin-camera
cordova plugin add cordova-plugin-device
cordova plugin add cordova-plugin-file
cordova plugin add cordova-plugin-geolocation
cordova plugin add cordova-plugin-media
cordova plugin add cordova-plugin-media-capture
cordova plugin add cordova-plugin-screen-orientation
cordova plugin add cordova-plugin-vibration
cordova plugin add cordova-plugin-app-exit
cordova plugin add cordova-plugin-purchase
```

### App Icon Resizer

```sh
https://appiconmaker.co
```

### Splash Screen/Image Sizing Table

```sh
size	   portrait	    landscape

ldpi	   200x320	    320x200
mdpi	   320x480	    480x320
hdpi	   480x800	    800x480
xhdpi	   720x1280	    1280x720
xxhdpi	   960x1600	    1600x960
xxxhdpi	   1280x1920	    1920x1280

<!-- Android 13 -->
<preference name="AndroidWindowSplashScreenAnimatedIcon" value="res/images/xxxhdpi.png" density="xxxhdpi"/>
<preference name="AndroidWindowSplashScreenAnimationDuration" value="3000"/>
<preference name="AndroidWindowSplashScreenBackground" value="#5e59f0"/>

<!-- Default | Android 10/11/12 -->
<splash src="res/screen/android/splash-port-ldpi.png" density="ldpi"/>
<splash src="res/screen/android/splash-port-mdpi.png" density="mdpi"/>
<splash src="res/screen/android/splash-port-hdpi.png" density="hdpi"/>
<splash src="res/screen/android/splash-port-xhdpi.png" density="xhdpi"/>
<splash src="res/screen/android/splash-port-xxhdpi.png" density="xxhdpi"/>
<splash src="res/screen/android/splash-port-xxxhdpi.png" density="xxhdpi"/>

<!-- Landscape Android 10/11/12 -->
<splash src="res/screen/android/splash-land-ldpi.png" density="land-ldpi" />
<splash src="res/screen/android/splash-land-mdpi.png" density="land-mdpi" />
<splash src="res/screen/android/splash-land-hdpi.png" density="land-hdpi" />
<splash src="res/screen/android/splash-land-xhdpi.png" density="land-xhdpi" />
<splash src="res/screen/android/splash-land-xxhdpi.png" density="land-xxhdpi" />
<splash src="res/screen/android/splash-land-xxxhdpi.png" density="land-xxxhdpi" />

<!-- Portrait Android 10/11/12 -->
<splash src="res/screen/android/splash-port-hdpi.png" density="port-hdpi" />
<splash src="res/screen/android/splash-port-ldpi.png" density="port-ldpi" />
<splash src="res/screen/android/splash-port-mdpi.png" density="port-mdpi" />
<splash src="res/screen/android/splash-port-xhdpi.png" density="port-xhdpi" />
<splash src="res/screen/android/splash-port-xxhdpi.png" density="port-xxhdpi" />
<splash src="res/screen/android/splash-port-xxxhdpi.png" density="port-xxxhdpi" />
```

### Allowing http request

```sh
Step 1 - add android:networkSecurityConfig="@xml/network_security_config" & android:usesCleartextTraffic="true" inside AndroidManifest.xml file.

Ex. <application 
	android:networkSecurityConfig="@xml/network_security_config" 
	android:usesCleartextTraffic="true">
    </application>

2. Go to res/xml/ directory and create a file network_security_config.xml 
3. Inside network_security_config.xml put this code:

<?xml version="1.0" encoding="utf-8"?>
<network-security-config>
    <base-config cleartextTrafficPermitted="true">
        <trust-anchors>
            <certificates src="system" />
        </trust-anchors>
    </base-config>
</network-security-config>

https://cordova.apache.org/docs/en/dev/guide/appdev/allowlist/
```
