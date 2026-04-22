# AdMobANE
**AdMob ANE - Support Google AdMob Ads in Air Android apps**

> This extension is built with the latest version of the Google Ads
> Library - 2026  (25.2.0)

** AdMob Ads Types  supports**

 - [x] AppOpen
 - [x] Banner
 - [x] Interstitial
 - [x] Rewarded Video

**AdMob Events**

**Preparation**
initAdMob

**App Open**  
 - loadAppOpen
 - showAppOpen
 - isAppOpenLoaded

**Banner**
 - showBanner
 - hideBanner
 - removeBanner
  
**Interstitial**  
 - loadInterstitial
 - showInterstitial
 - isInterstitialLoaded

**Rewarded**  
 - loadRewarded
 - showRewarded
 - sRewardedLoaded

**AdMob Settings**
 - setVolume
 - setMuted
 - setChildDirected
 - addTestDevice

## ****integrate AdMob ANE into your application****

***Begin by defining the following  - variables Google's experimental IDs (for testing only)***

    const BANNER_ID: String = "ca-app-pub-3940256099942544/6300978111";
    const INTERSTITIAL_ID: String = "ca-app-pub-3940256099942544/1033173712";
    const REWARDED_ID: String = "ca-app-pub-3940256099942544/5224354917";
    const APP_OPEN_ID: String = "ca-app-pub-3940256099942544/9257395921";

***Edit your app XML description file as follows - change the Google Test App ID to your app ID.***

    <manifestAdditions><![CDATA[
        <manifest android:installLocation="auto">

			<uses-sdk android:minSdkVersion="23" android:targetSdkVersion="34" />

            <uses-permission android:name="android.permission.INTERNET"/>
            <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
            <uses-permission android:name="com.google.android.gms.permission.AD_ID"/>
            <application>
					
                <meta-data
                    android:name="com.google.android.gms.ads.APPLICATION_ID"
                    android:value="ca-app-pub-3940256099942544~3347511713"/>

                <activity
                    android:name="com.google.android.gms.ads.AdActivity"
                    android:configChanges="keyboard|keyboardHidden|orientation|screenLayout|uiMode|screenSize|smallestScreenSize"
                    android:exported="false"
                    android:theme="@android:style/Theme.Translucent"/>
            </application>
        </manifest>
    ]]></manifestAdditions>
    
