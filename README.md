[![Build Status](https://travis-ci.org/kaltura/player-sdk-native-android.svg?branch=master)](https://travis-ci.org/kaltura/player-sdk-native-android)

# player-sdk-native-android
Player SDK Native Android
=========================
For detailed usage guide see [Knowledge Center Android player SDK usage guide](http://knowledge.kaltura.com/kaltura-player-sdk-android)

**Note**: The Kaltura native player component is in beta. If your a Kaltura customer please contact your Kaltura customer success manager to help facilitate use of this component. 

The Kaltura player-sdk-native component enables embedding the [kaltura player](http://player.kaltura.com) into native environments. This enables full HTML5 player platform, without limitations of HTML5 video tag API in Android platforms. Currently for Android this enables: 
* Inline playback with HTML controls ( disable controls during ads etc. ) 
* Widevine DRM support
* AutoPlay 
* Volume Control
* Full [player.kaltura.com](http://player.kaltura.com) feature set for themes and plugins

For a full list of native embed advantages see native controls table within the [player toolkit basic usage guide](http://knowledge.kaltura.com/kaltura-player-v2-toolkit-theme-skin-guide). 

The Kaltura player-sdk-native component can be embedded into both native apps, and hybrid native apps ( via standard dynamic embed syntax ) 

![alt text](http://html5video.org/presentations/HTML5PartDeux.FOSDEM.2014/player-native.png "player in native")
![alt text](http://html5video.org/presentations/HTML5PartDeux.FOSDEM.2014/player-native2.png "player in webview")

Future support will include: 
* PlayReady DRM
* Multiple stream playback
* Offline viewing

Architecture Overview
=====
![alt text](http://html5video.org/presentations/HTML5PartDeux.FOSDEM.2014/koverview.jpg "Architecture Overview")


Quick Start Guide
======

```
1. git clone https://github.com/kaltura/player-sdk-native-android.git to the same folder of your app.
```
```
2. Add reference to PlayerSDK module from your project:
```

#####Select `settings.gradle` and add:

```
include ':castCompanionLibraryandroid'
project(':castCompanionLibraryandroid').projectDir=new File('../player-sdk-native-android/castCompanionLibraryandroid')
 
include ':exoPlayerLib'
project(':exoPlayerLib').projectDir=new File('../player-sdk-native-android/exoPlayerLib')
 
include ':googlemediaframework'
project(':googlemediaframework').projectDir=new File('../player-sdk-native-android/googlemediaframework')
 
include ':hLSPlayerSDK'
project(':hLSPlayerSDK').projectDir=new File('../player-sdk-native-android/hLSPlayerSDK')
 
include ':playerSDK'
project(':playerSDK').projectDir=new File(‘../player-sdk-native-android/playerSDK')
```
#####Right click on your app folder ->`Open Module Settings`.

![alt text](https://9e7704fa-a-62cb3a1a-s-sites.googlegroups.com/site/kalturaimages/shareicons/ModuleSettings.png?attachauth=ANoY7co3Fibe4sZcIY5K1QBU7L74Y4Jp71WJbMJ4vKagckhsYzA2qxzAT5myeKeizQrUsOqn7c-MCNU6jKJi-SZwMWHv2JMcmM7xs-O2FkQUoebdD7SFScNdrUV8sfdaAq0GrNYgrSEk0_4S0bYErXbg0nEzLlOHLOURwMzhZsEvMFdjj_Qe6vfUCsFdlOm6BHOV8FjrA8azbx-ywPWn13SirFrVD71PmbrMftmv6NivJOzaes9lois%3D&attredirects=0)

#####Select `Dependencies` tab -> click on the `+` button and choos the `playerSDK` module:
![alt text](https://9e7704fa-a-62cb3a1a-s-sites.googlegroups.com/site/kalturaimages/shareicons/AddDependencies.png?attachauth=ANoY7cqDWyp0Wk-K-EcsLqf1Iad71Hm8WXS55nmpkaKjw6Me79OXBPoUb8_utColKQgLHC-NL8Q4MD6jabqeUvnYiW9nANA_kcjGbgx8tFndx-_nwrdKLawmpJYN24XMl2g9EvR6SfVwLpMHOymUnN868yvIJQiIOeYpVjtKW67Fr13tD3mVVMSzqoPC1hbTnMiJE-r6msrIkqy4SZFsTXk39swMea7UAEN1heb6u_AdsU-UxUBfTyg%3D&attredirects=0)

Now, you are linked to the playerSDK by reference. Be sure that you cloned the playerSDK to the same folder of your project.


Make sure that you cloned the **_player-sdk-native-android_** project to the same folder of your project, if you prefer to clone it else where, you should update the **`settings.gradle`**. 

API Overview
=====

The player includes the same KDP api available in webviews this includes: 
* kdp.asyncEvaluate( property, callback );
* kdp.setKDPAttribute( property, value );
* kdp.addListener( name, callback );
