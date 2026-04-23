# AdMobANE
**AdMob ANE - Support Google AdMob Ads in Air Android apps**

> This extension is built with the latest version of the Google Ads  Library - 2026  (25.2.0)

**AdMob Ads Types Supports**

 - [x] AppOpen
 - [x] Banner
 - [x] Interstitial
 - [x] Rewarded Interstitial
 - [x] Rewarded Video

## ****integrate AdMob ANE into your application****

***Begin by defining the following  - variables Google's experimental IDs (for testing only)***

    const APP_ID: String = "ca-app-pub-3940256099942544~3347511713"; // Test App ID
    const BANNER_ID: String = "ca-app-pub-3940256099942544/6300978111"; // Test Banner
    const INTERSTITIAL_ID: String = "ca-app-pub-3940256099942544/1033173712"; // Test Interstitial
    const REWARDED_ID: String = "ca-app-pub-3940256099942544/5224354917"; // Test Rewarded
    const REWARDED_INTERSTITIAL_ID: String = "ca-app-pub-3940256099942544/5354046379"; // Test Rewarded Interstitial
    const APP_OPEN_ID: String = "ca-app-pub-3940256099942544/9257395921"; // Test App Open

## **Importing library classes**

    import com.admob.mx.AdMobANE;
    import com.admob.mx.AdMobEvent;
	
## **Preparation**

    var adMob: AdMobANE; // The single reference to the ANE (Singleton)

## **AdMob Settings**

**Content Rating**
>
    adMob.setMaxContentRating(AdMobANE.RATING_PG); // parental guidance suggested
    
**Child Protection**
>
    adMob.setChildDirected(false); // COPPA — not for children
 >
    adMob.setUnderAgeOfConsent(false); // GDPR — above age of consent

**Audio**
>
    adMob.setVolume(0.8); // 80% volume
>
    adMob.setMuted(false); // not muted

**Test Device**
>
    adMob.addTestDevice("xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"); // ← replace with your device ID

>Get deviceId from logcat by searching for "Use RequestConfiguration"


**Initialize First, it is necessary**
>
    adMob.initAdMob(APP_ID);
>
**load the ads to view**
>
    adMob.loadAppOpen(APP_OPEN_ID);
	adMob.loadInterstitial(INTERSTITIAL_ID);
	adMob.loadRewardedInterstitial(REWARDED_INTERSTITIAL_ID);
	adMob.loadRewarded(REWARDED_ID);

**Banner show instantly and does not require loading.**
>
adMob.showBanner(
    BANNER_ID, // Banner ID
    AdMobANE.BANNER_BOTTOM, // Position 
    AdMobANE.SIZE_ADAPTIVE // Adaptive size (Recommended for GMA v25+)
);


## **AdMob Events**

**Initialize**
>
    adMob.addEventListener(AdMobANE.ADMOB_INITIALIZED, _onInitialized);
>
    adMob.addEventListener(AdMobANE.ADMOB_INIT_FAILED, _onInitFailed);

**App Open**  
>
    adMob.addEventListener(AdMobANE.APP_OPEN_LOADED, _onAppOpenLoaded);
>
    adMob.addEventListener(AdMobANE.APP_OPEN_LOAD_FAILED, _onAppOpenFailed);
 >
    adMob.addEventListener(AdMobANE.APP_OPEN_SHOWED, _onAppOpenShowed);
>
    adMob.addEventListener(AdMobANE.APP_OPEN_SHOW_FAILED, _onAppOpenShowFailed);
>
    adMob.addEventListener(AdMobANE.APP_OPEN_CLOSED, _onAppOpenClosed);
>
    adMob.addEventListener(AdMobANE.APP_OPEN_IMPRESSION, _onAppOpenImpression);
>
    dMob.addEventListener(AdMobANE.APP_OPEN_DESTROYED, _onAppOpenDestroyed);	

**Banner**
>
    adMob.addEventListener(AdMobANE.BANNER_LOADED, _onBannerLoaded);
>
    adMob.addEventListener(AdMobANE.BANNER_LOAD_FAILED, _onBannerFailed);
>
    adMob.addEventListener(AdMobANE.BANNER_OPENED, _onBannerOpened);
>
    adMob.addEventListener(AdMobANE.BANNER_CLOSED, _onBannerClosed);
>
    adMob.addEventListener(AdMobANE.BANNER_IMPRESSION, _onBannerImpression);
>
    adMob.addEventListener(AdMobANE.BANNER_CLICKED, _onBannerClicked);
>
    adMob.addEventListener(AdMobANE.BANNER_REFRESHED, _onBannerRefreshed);
>
    adMob.addEventListener(AdMobANE.BANNER_REFRESH_FAILED, _onBannerRefreshFailed);
>
    adMob.addEventListener(AdMobANE.BANNER_POSITION_CHANGED, _onBannerPositionChanged);
>
    adMob.addEventListener(AdMobANE.BANNER_POSITION_FAILED, _onBannerPositionFailed);
>
    adMob.addEventListener(AdMobANE.BANNER_HIDDEN, _onBannerHidden);
>
    adMob.addEventListener(AdMobANE.BANNER_REMOVED, _onBannerRemoved);
  
**Interstitial**  
>
    adMob.addEventListener(AdMobANE.INTERSTITIAL_LOADED, _onInterstitialLoaded);
 >
    adMob.addEventListener(AdMobANE.INTERSTITIAL_LOAD_FAILED, _onInterstitialFailed);
>
    adMob.addEventListener(AdMobANE.INTERSTITIAL_SHOWED, _onInterstitialShowed);
 >
    adMob.addEventListener(AdMobANE.INTERSTITIAL_SHOW_FAILED, _onInterstitialShowFailed);
>
    adMob.addEventListener(AdMobANE.INTERSTITIAL_CLOSED, _onInterstitialClosed);
>
    adMob.addEventListener(AdMobANE.INTERSTITIAL_IMPRESSION, _onInterstitialImpression);
>
    adMob.addEventListener(AdMobANE.INTERSTITIAL_DESTROYED, _onInterstitialDestroyed);

**Rewarded Interstitial**
>
    adMob.addEventListener(AdMobANE.REWARDED_INTERSTITIAL_LOADED, _onRILoaded);
>
    adMob.addEventListener(AdMobANE.REWARDED_INTERSTITIAL_LOAD_FAILED, _onRIFailed);
>
    adMob.addEventListener(AdMobANE.REWARDED_INTERSTITIAL_SHOWED, _onRIShowed);
>
    adMob.addEventListener(AdMobANE.REWARDED_INTERSTITIAL_SHOW_FAILED, _onRIShowFailed);
>
    adMob.addEventListener(AdMobANE.REWARDED_INTERSTITIAL_CLOSED, _onRIClosed);
>
    adMob.addEventListener(AdMobANE.REWARDED_INTERSTITIAL_IMPRESSION, _onRIImpression);
>
    adMob.addEventListener(AdMobANE.REWARDED_INTERSTITIAL_REWARD, _onRIReward);
>
    adMob.addEventListener(AdMobANE.REWARDED_INTERSTITIAL_DESTROYED, _onRIDestroyed);

**Rewarded**  
>
    adMob.addEventListener(AdMobANE.REWARDED_LOADED, _onRewardedLoaded);
>
    adMob.addEventListener(AdMobANE.REWARDED_LOAD_FAILED, _onRewardedFailed);
>
    adMob.addEventListener(AdMobANE.REWARDED_SHOWED, _onRewardedShowed);
>
    adMob.addEventListener(AdMobANE.REWARDED_SHOW_FAILED, _onRewardedShowFailed);
>
    adMob.addEventListener(AdMobANE.REWARDED_CLOSED, _onRewardedClosed);
>
    adMob.addEventListener(AdMobANE.REWARDED_IMPRESSION, _onRewardedImpression);
>
    adMob.addEventListener(AdMobANE.REWARDED_REWARD, _onRewardedReward);
>
    adMob.addEventListener(AdMobANE.REWARDED_DESTROYED, _onRewardedDestroyed);
	
**UMP Consent**
>
    adMob.addEventListener(AdMobANE.CONSENT_INFO_UPDATED, _onConsentInfoUpdated);
>
    adMob.addEventListener(AdMobANE.CONSENT_INFO_FAILED, _onConsentInfoFailed);
>
    adMob.addEventListener(AdMobANE.CONSENT_FORM_DISMISSED, _onConsentFormDismissed);
>
    adMob.addEventListener(AdMobANE.CONSENT_FORM_FAILED, _onConsentFormFailed);


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



***A simple example of AppOpen AD***

	if (adMob.isAppOpenLoaded()) {

		adMob.showAppOpen(); // App Open

	} else {

		adMob.loadAppOpen(APP_OPEN_ID);

	}
	
***A simple example of Interstitial AD***

	if (adMob.isInterstitialLoaded()) {

		adMob.showInterstitial();

	} else {

		adMob.loadInterstitial(INTERSTITIAL_ID);
	}

***A simple example of Rewarded Interstitial AD***

		if (adMob.isRewardedInterstitialLoaded()) {

		adMob.showRewardedInterstitial();

	} else {

		adMob.loadRewardedInterstitial(REWARDED_INTERSTITIAL_ID);
	}
	
***A simple example of Rewarded AD***

    adMob.addEventListener(AdMobANE.REWARDED_REWARD, _onRewardedReward);
>
   
        	
        	if (adMob.isRewardedLoaded()) {
        
        		adMob.showRewarded();
        
        	} else {
        
        		adMob.loadRewarded(REWARDED_ID);
        	}
 >
          	
    function _onRewardedReward(e: AdMobEvent): void {
    
    	trace("[Rewarded] 🎁: " + e.rewardAmount + " " + e.rewardType);
    	
    }
	

 1. AdMobANE.ane Attached is a file ready for embedding in your app.
 
 2. Also included is an example application with all the necessary cases to you
 
 3.  And there is a step-by-step guide on how to create your own.

***Made with much passion and patience to use it for free***

> Thanks lilili87222 for the idea.
> 
> Thanks nboy1 for the hope.
> 
> Thanks chatgpt / cloud ai for making things easier.
> 
> Thanks to me for my patience.
> 
> **Thank God (الله) for everything.**


***Screenshots of ads in test mode***

<p align="center">
  <img src="https://github.com/user-attachments/assets/85a64a4a-4e54-4356-b9b6-09963faf335e" width="32%" />
  <img src="https://github.com/user-attachments/assets/50776293-5ddd-4934-bf93-74df238cc7eb" width="32%" />
  <img src="https://github.com/user-attachments/assets/ddfadec1-44c2-4f26-867b-af23bddbc6cc" width="32%" />
</p>

