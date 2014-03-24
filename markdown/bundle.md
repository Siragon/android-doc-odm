Siragon Implementation Instructions        03/19/2014

Siragon

Implementation Instructions


1. The Bundle
a. Bundle Download Link:
b. Bundle contents (files by folder):
c. Bundle contents (by app):
2. Implementation:
Bundle
Default Search and Homepage
3. Verification:
Device Manager
Accuweather
iMediaShare
Maxthon
Despegar
Lookout Mobile Security & Antivirus
OfficeSuite
PlayKids
FreeZone Free WiFi
Opera Mini
Yahoo! Default Search
Yahoo! Default Home Page
Kido’z
SwiftKey Trial
________________


1. The Bundle

a. Bundle Download Link:  
https://github.com/Siragon/appattach-bundle-app/archive/master.zip


b. Bundle contents (files by folder):
* system\
   * aapreinstall\
      * AppAttach-3.apk
      * com.accuweather.android.apk
      * com.bianor.ams.apk
      * com.gm.despegar.apk
      * com.kidoz.apk
      * com.lookout.apk
      * com.mobisystems.editor.office_app_attach.apk
      * com.movile.playkids.apk
      * com.mx.browser.apk
      * com.opera.mini.apk
      * com.touchtype.swiftkey.phone.trial.apk
      * net.alouw.alouwCheckin.apk
   * app\
      * DeviceManager_305.apk
   * etc\
      * devicemanager.cfg


c. Bundle contents (by app):
* DeviceManager
* AccuWeather
* Maxthon
* iMediaShare
* Despegar
* Lookout Mobile Security & Antivirus
* OfficeSuite
* PlayKids
* FreeZone Free WiFi
* Opera Mini
* Kido’z
* SwiftKey
________________


2. Implementation:
Bundle
* Download the bundle: (Siragon_apps_2014-03-19.zip)
* Extract the bundle to your hard drive.
* Merge the bundle directory tree with that of the device image.
* Confirm that each file is placed in the correct folder. (Refer to section 1-b)
* Flash the modified image to your test device.


**for testing purposes, the files may be pushed to a rooted device via adb and then the device factory reset. In both cases, the files are present on the device when it is booted for the first time.


Default Search and Homepage
* Configure the stock browser to the correct default URLs for search and homepage:
   * Set homepage as one of the following:
Desktop style: http://es.yahoo.com/?fr=appattach&type=233
Mobile style: http://es.yhs4.search.yahoo.com/yhs/mobile/web?hspart=appattach&hsimp=yhsm-appattach&type=233
   * Set Default Search as: http://es.yhs4.search.yahoo.com/yhs/mobile/search?hspart=appattach&hsimp=yhsm-appattach&type=230&p={searchTerms}


________________


3. Verification:
   * Verify each app is present on the device. (Refer to section 1-c)
   * Device Manager is not visible in the app drawer. This is normal.
   * Connect the device to the internet.
   * Verification steps for each app below:


Device Manager
Device Manager reports device information for trending and analysis. It will automatically report shortly after being turned on and connected to the internet for the first time.


   * Confirm device activation received using the test tracker. 
 
You may see your test activity in real-time using our test tracker here: http://devmgr.net/testing
   * The page requires authentication: username: testing password: dmTesting
   * By default, this page will not show any events. Entering the full "mac_address" of a known device will show any activity from that device.
Accuweather
   * Go through first-run and confirm proper operation and functionality.
   * Open Accuweather and then key in "adopstest" into the location entry (far-left panel). "Partner" line should read: "androidappattach_000370".
   * Confirm app events are tracked using the test tracker.


Accuweather reports the following events:
   * Installed - Automatically when the app is installed on first boot.
   * Launched - Every time the app is opened.
   * Activated - When the first-run user agreement is accepted.
   * AdDisplayed - Each time a new advertisement is displayed within the Accuweather UI.


You may see your test activity in real-time using our test tracker here: http://devmgr.net/testing
   * The page requires authentication: username: testing password: dmTesting
   * By default, this page will not show any events. Entering the full "mac_address" of a known device will show any activity from that device.
iMediaShare
   * Go through first-run and confirm proper operation and functionality.
Maxthon
   * Go through first-run and confirm proper operation and functionality.
   * Please Type mx://info into the URL bar.
   * Confirm that the resulting "About Maxthon Cloud Browser" dialog box “Partner Code” reads: 620024890100.
Despegar
   * Go through first-run and confirm proper operation and functionality.
Lookout Mobile Security & Antivirus
   * Go through first-run and confirm proper operation and functionality.
   * Sign up for a new Lookout account 
   * Make note of the email address used to sign up.
   * Test the app for functionality and user experience on your device(s).
   * Send an email to custserv@appattach.com and/or to your technical contact at appAttach containing the email address used to sign up for Lookout.
OfficeSuite
   * Go through first-run and confirm proper operation and functionality.
   * Open OfficeSuite and then tap on “buy". This will open a browser window.
   * (Optional) Purchase a license and activate the software.


OfficeSuite reports the following events:
   * Installed - Automatically when the app is installed on first boot.
   * Launched - Every time the app is opened.
   * BuyNow - When the “Buy” button is tapped.
   * Purchased - When a purchased activation code is entered into the app, activating the full version.


You may see your test activity in real-time using our test tracker here: http://devmgr.net/testing
   * The page requires authentication: username: testing password: dmTesting
   * By default, this page will not show any events. Entering the full "mac_address" of a known device will show any activity from that device.
PlayKids
   * Go through first-run and confirm proper operation and functionality.
   * Confirm app events are tracked using the test tracker.


Playkids reports the following events:
   * Installed - Automatically when the app is opened for the first time.
   * Launched - Every time the app is opened.
   * Subscription - When a Playkids trial subscription converts to a paid subscription.


You may see your test activity in real-time using our test tracker here: http://devmgr.net/testing
   * The page requires authentication: username: testing password: dmTesting
   * By default, this page will not show any events. Entering the full "mac_address" of a known device will show any activity from that device.
FreeZone Free WiFi
   * Go through first-run and confirm proper operation and functionality.
   * Confirm app events are tracked using the test tracker.


FreeZone reports the following events:
   * Install - Automatically when the app is opened for the first time.
   * Open - Every time the app is opened.
   * Subscription - When a FreeZone trial subscription converts to a paid subscription.


You may see your test activity in real-time using our test tracker here: http://devmgr.net/testing
   * The page requires authentication: username: testing password: dmTesting
   * By default, this page will not show any events. Entering the full "mac_address" of a known device will show any activity from that device.
Opera Mini
   * Go through first-run and confirm proper operation and functionality.
   * Open the information display by entering “debug:” into the URL bar.
   * If correct, line: “Branding” will report your unique ID: “appAttach-3”.
Yahoo! Default Search
   * Run a search and verify results page URL contains “type=230”
Yahoo! Default Home Page
   * Confirm the default home page matches your assigned URL
   * Run a search and verify results page URL contains “type=233”
Kido’z
   * Go through first-run and confirm proper operation and functionality.
   * Sign up for an account. Make note of the email address used.
   * Contact your appAttach representative, notifying them of the email address used to test.
   * Receive confirmation from appAttach that the user activity was tracked correctly.
SwiftKey Trial
   * Go through first-run and confirm proper operation and functionality.
   * Confirm the file: /data/data/com.touchtype.swiftkey.phone.trial/shared_prefs/com.touchtype.swiftkey.phone.trial_preferences.xml includes “utm_source=appAttach_preload_000497”
   * Upgrade to Premium version.
   * After upgrade, confirm the file: "/data/data/com.touchtype.swiftkey/shared_prefs/com.touchtype.swiftkey_preferences.xml" includes “utm_source=appAttach_preload_000497”
   * Contact your appAttach representative, notifying them of your test and including your Google Play order number.
   * Receive confirmation from appAttach that the user activity was tracked correctly.
