# Grindr Privacy Leaks

SVT and SINTEF conducted an experiment the 7th of February 2018 to analyse privacy leaks in the dating application Grindr. This was realised for the Sweedish TV program "Plus granskar", that you [may watch online.](https://www.svtplay.se/video/17267438/plus-granskar/plus-granskar-ditt-karleksliv-en-handelsvara)

We discovered that Grindr contains many trackers, and shares personal information with various third parties directly from the application.


## Grindr Shares Personal Information With Third-Parties

|Data|Sent to third-parties using unsafe HTTP ⚠ and HTTPS|Sent to third-parties using HTTPS only|
|----|--------------------------------|---------------------------|
|Grindr (App Name)|Adrta, Google,Liftoff, Manage.com, Mobfox, Mopub, OpenX, Smatoo|AdColony, Adsafeprotected, Apple, AppsFlyer, Apptimize, Crashlytics, Facebook, Fqtag, Kochava, Localytics, Moatads, TreasureData
|Precise GPS Position|Adrta,Liftoff, Mopub, Nexage, OpenX|Apptimize, Localytics, Treasure Data
|Gender|Adrta, Mopub, Smatoo|Apptimize, Localytics
|HIV Status||Apptimize, Localytics
|Last Tested Date||Apptimize, Localytics
|Email||Localytics
|Age|Mopub, Smatoo|Apptimize, Localytics
|Height||Apptimize, Localytics
|Weight||Apptimize, Localytics
|Body Type||Apptimize, Localytics
|Position (sexual)||Apptimize, Localytics
|Grindr Profile ID||AdColony, Apptimize, Crashlytics, Localytics, TreasureData
|Tribe (Bear, Clean Cut, Daddy, Discreet, Geek, Jock, Leather, Otter Poz, Rugged, Trans, Unknown)|Mopub|Apptimize, Localytics
|Looking For (Chat, Dates, Friends, Networking, Relationship, Right Now, Unkown)|Mopub|Apptimize, Localytics
|Etchnicity|Mopub|Apptimize, Localytics
|Relationship Status|Mopub|Apptimize, Localytics
|Phone ID|Liftoff, Adrta, Mopub, Smatoo|AdColony, Kochava,
|Advertising ID|Adrta,Liftoff, Mopub, Mopub, Nexage, OpenX, Smatoo|AdColony, Adsafeprotected, AppsFlyer, Apptimize, Facebook, Fqtag, Localytics, Maxads, TreasureData
|Phone Characteristics|Adrta,Liftoff, Mopub, OpenX, Smatoo|AdColony, AppsFlyer, Apptimize, Facebook, Maxads, TreasureData
|Language|Liftoff, Mopub, Nexage, Smatoo|AdColony, AppsFlyer, Apptimize, Facebook, Maxads, TreasureData
|Activity||App-measurement, Apptimize, Facebook, TreasureData
|Pictures|||
|Messages content|||

![](https://raw.githubusercontent.com/SINTEF-9012/grindr-privacy-leaks/master/screenshot-apptimize-1.PNG)
![](https://raw.githubusercontent.com/SINTEF-9012/grindr-privacy-leaks/master/screenshot-localytics-1.PNG)

## Grindr Shares Personal Information Including HIV Status With Apptimize And Localytics

It is unnecessary for Grindr to track its users HIV Status using third-parties services. Moreover, these third-parties are not necessarily certified to host medical data, and Grindr's users may not be aware that they are sharing such data with them.

## Grindr Shares Personal Information Without Security

Personal information is shared unencrypted, allowing people, companies, or governments to listen on a network to discover who is using Grindr, where they are precisely located during a day, how do they look, what do they like, what do they browse… By sharing such information in an unsafe way, Grindr is exposing its users.

## Grindr Contains Trackers

By decompiling the Grindr Android source code, we discovered tracking software. Notably Facebook, Smatoop or Localytics. [This is also confirmed by the project Exodus.](https://reports.exodus-privacy.eu.org/reports/5323/)

## Experiment Setup

We installed Grindr on a Samsung Galaxy running Android and on an iPhone running iOS. Two persons created a Grindr profile and started dating for a few minutes.

We analysed the Grindr network traffic by using a man-in-the-middle proxy recording HTTP and HTTPS exchanges, using a setup similar to the one described in the paper ["Who knows what about me? A survey of behind the scenes personal data sharing to third parties by mobile apps." (Zang, K., Dummit, J., Graves, P.L. and Latanya, S.  - Technology Science (2015)."](https://techscience.org/a/2015103001/download.pdf) 
We used Wireshark to monitor all TCP/IP traffic, Fiddler to capture HTTP and HTTPS traffic, and APKTool to decompile the Android application.

## Raw Data

You will find this experiment's HTTP and HTTPS raw data in this repository.
