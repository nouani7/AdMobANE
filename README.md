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
