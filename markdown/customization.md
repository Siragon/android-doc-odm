###Customization
####Default wallpaper
The ```framework-res.apk``` contain the ```default_wallpaper.jpg```
```text
    /system/framework/framework-res.apk
    /res/drawable-nodpi/default_wallpaper.jpg
```
Check the size to select.

Click to download.

**1920x1080**

[![](/android-doc-odm/res/wallpapers/1920x1080/wallpaper1.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1080/wallpaper1.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1080/wallpaper2.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1080/wallpaper2.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1080/wallpaper3.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1080/wallpaper3.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1080/wallpaper4.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1080/wallpaper4.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1080/wallpaper5.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1080/wallpaper5.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1080/wallpaper6.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1080/wallpaper6.jpg)

**1920x1280**

[![](/android-doc-odm/res/wallpapers/1920x1280/wallpaper1.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1280/wallpaper1.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1280/wallpaper2.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1280/wallpaper2.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1280/wallpaper3.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1280/wallpaper3.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1280/wallpaper4.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1280/wallpaper4.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1280/wallpaper5.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1280/wallpaper5.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1280/wallpaper6.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1280/wallpaper6.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1280/wallpaper7.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1280/wallpaper7.jpg)

**1920x1408**

[![](/android-doc-odm/res/wallpapers/1920x1408/wallpaper1.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1408/wallpaper1.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1408/wallpaper2.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1408/wallpaper2.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1408/wallpaper3.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1408/wallpaper3.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1408/wallpaper4.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1408/wallpaper4.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1408/wallpaper5.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1408/wallpaper5.jpg)
[![](/android-doc-odm/res/wallpapers/1920x1408/wallpaper6.thumbnail.jpg)](/android-doc-odm/res/wallpapers/1920x1408/wallpaper6.jpg)

####Boot Screen Customization
At startup, Android displays a splashscreen image while booting the device. Do the following if you wish to modify the default splash screen:

Create a 320x480 image, splashscreen.jpg in this example.
Using ImageMagick, convert your .jpg file to .r format:
 ```bash
	convert screen.jpg screen.r
```
Use the rgb2565 application to convert the image to 565 format:
```bash
rgb2565 < screen.rgb > screen.565
```
Use fastboot to flash the image to the device:
```bash
fastboot flash splash1 screen.565
```
####Network Customization Platform
Network Configuration

Android stores network configurations as a resource that gets compiled into binary at form at build time. The XML representation of this resource is located at //android/frameworks/base/core/res/res/xml/apns.xml. This file does not include any configured APNs. You should not modify this file, but instead configure APNs by product at build time (see Build-time APN Configuration below).

Each network configuration for Venezuela is stored in an XML element following this syntax:

```xml
<apn carrier="Digitel" 
        mcc="734" 
        mnc="02" 
        apn="gprsweb.digitel.ve" 
        proxy="" 
        mmsc="" 
        mmsproxy="" 
        mmsport="" 
        type="default" />
 <apn carrier="Digitel MMS" 
		mcc="734" 
        mnc="02" 
        apn="expresate.digitel.ve" 
        proxy="" 
        mmsc="http://mms.412.com.ve/servlets/mms" 
        mmsproxy="10.99.0.10" 
        mmsport="8080" 
        type="mms" />
  <apn carrier="Movistar VE" 
        mcc="734" 
        mnc="04" 
        apn="internet.movistar.ve" 
        proxy="" 
        mmsc="" 
        mmsproxy="" 
        mmsport="" 
        type="default" />
  <apn carrier="Movistar MMS" 
        mcc="734" 
        mnc="04" 
        apn="mms.movistar.ve" 
        proxy="" 
        mmsc="http://mms.movistar.com.ve:8088/mms" 
        mmsproxy="200.35.64.73" 
        mmsport="9001" 
        type="mms" />
  <apn carrier="Movilnet" 
		mcc="734" 
        mnc="06" 
		apn="int.movilnet.com.ve" 
        type="default" />
  <apn carrier="Movilnet MMS" 
		mcc="734" 
		mnc="06" 
		apn="mm.movilnet.com.ve" 
		mmsc="http://mms2.movilnet.com.ve/servlets/mms" 
		mmsproxy="192.168.16.12" 
		mmsport="8080" 
		type="mms" />
```
####Build-time APN configuration

To set the APN configuration for a particular product target, add an apns-conf.xml file to the product configuration (do not modify the default platform APNs). This allows multiple products, all with different APNs, to be built off the same code base.

To configure APNs at the product level, add a line to the product configuration file like the example below (vendor/siragon/products/myphone-us.mk):

```text
PRODUCT_COPY_FILES := vendor/siragon/etc/apns-conf-us.xml:system/etc/apns-conf.xml
```
####APN configuration at run time
At runtime, the Android reads APNs from the following file:
```text 
system/etc/apns-conf.xml
```
Android supports the following run-time network configuration methods to choose the appropriate APN from the list of configured APNs:

**Automatic Configuration:** At boot time, Android determines the correct network configuration based on the MCC and MNC from the SIM card and automatically configure all network settings.

**Manual Configuration:** The platform will also support runtime (user) manual selection of network settings by name, for example, "Company Name US," and will support manual network configuration entry.

**WAP / SMS Push Configuration:** The network configurations are standard Android resources. You can upgrade a resource at runtime by installing a new system resource APK package. It will be possible to develop a network configuration service which listens to a specific binary SMS port for binary SMS messages containing the network configurations. NOTE: The implementation will likely be network operator dependent due to inconsistent SMS ports, binary SMS formats, etc.

####Customizing pre-loaded applications
To customize the list of Android packages for a particular product (applications, input methods, providers, services, etc.), set ```PRODUCT_PACKAGES``` property in the product configuration, as illustrated below:

```makefile
PRODUCT_PACKAGES := \
 <company_name>Mail \
    <company_name>IM \
 <company_name>HomeScreen \
 <company_name>Maps \
 <company_name>SystemUpdater
 ```
Package names should correspond to the LOCAL_PACKAGE_NAME specified for each package's build target. For example, the Android.mk build target for <company_name>Mail, referenced above, could look like this:

```makefile
# Build the <company_name>Mail application
LOCAL_PATH:= $(call my-dir)
include $(CLEAR_VARS)
 
LOCAL_MODULE_TAGS := user development
 
LOCAL_SRC_FILES := $(call all-java-files-under,src,tests)
 
LOCAL_STATIC_JAVA_LIBRARIES := <company_name>login-client
 
# Specify the package name
LOCAL_PACKAGE_NAME := <company_name>Mail
 
# Specify the certificate used to sign the application
LOCAL_CERTIFICATE := vendor/siragon/certs/app
 
include $(BUILD_PACKAGE)
 
# Build the login client static library
include $(LOCAL_PATH)/client/Android.mk
```
Note that the home screen is just an Android application that can be replaced entirely or customized by changing source code and application resources (Java source, layouts, etc.).

####Customizing browser bookmarks
Browser bookmarks are stored as string resources in the Browser application: //android/packages/apps/Browser/res/values/strings.xml. Bookmarks are defined as simple value string arrays called "bookmarks". Each bookmark entry is stored as a pair of array values; the first represents the bookmark name and the second the bookmark URL. For example:

```xml
<!-- Bookmarks -->
<string-array name="bookmarks">
    <item>Síragon</item>
    <item>http://www.siragon.com/</item>
    <item>Síragon Sync</item>
    <item>http://sync.siragonplay.com/</item>
    <item>Síragon Play</item>
    <item>http://www.siragonplay.com/</item>
    <item>Google</item>
    <item>http://www.google.com/</item>
    <item>Yahoo!</item>
    <item>http://es.yhs4.search.yahoo.com/yhs/mobile/web?hspart=appattach&hsimp=yhsm-appattach&type=233</item>
    <item>Facebook</item>
    <item>http://www.facebook.com/</item>
    <item>Wikipedia</item>
    <item>http://www.wikipedia.org/</item>
    <item>CNN en Español</item>
    <item>http://cnnespanol.cnn.com/</item>
    <item>New York Times</item>
    <item>http://www.nytimes.com/</item>
    <item>ESPN</item>
    <item>http://espn.go.com/</item>
    <item>Amazon</item>
    <item>http://www.amazon.com/</item>
</string-array>
```
Like and Android application resource, the platform will load alternate resources based on the platform configuration values. See Resources and Internationalization in the Android SDK for details. To configure bookmarks for a specific mobile network operator, place your customized bookmarks in a separate strings.xml file and place it under a Mobile Network Code (MNO) specific resource folder. For example, Browser/res/values-mccXXX-mncYYY/strings.xml where XXX and YYY represent the three-digit MCC and two to three digit MNC values.

Android loads any configuration-specific resources as override values for the default values, so it is only necessary to include the bookmarks string-array values in this file.

####Email Provider Customization
The default email provider settings are stored as string resources in the Email application (//android/packages/apps/Email/res/xml/providers.xml) as illustrated below.
```xml
<providers>

 
<!-- Gmail variants -->
    <provider id="gmail" label="Gmail" domain="gmail.com">
        <incoming uri="imap+ssl+://imap.gmail.com" username="$email"/>
        <outgoing uri="smtp+ssl+://smtp.gmail.com" username="$email"/>
    </provider>
    <provider id="googlemail" label="Google Mail" domain="googlemail.com">
        <incoming uri="imap+ssl+://imap.googlemail.com" username="$email"/>
        <outgoing uri="smtp+ssl+://smtp.googlemail.com" username="$email"/>
    </provider>
    <provider id="google" label="Google" domain="google.com">
        <incoming uri="imap+ssl+://imap.gmail.com" username="$email"/>
        <outgoing uri="smtp+ssl+://smtp.gmail.com" username="$email"/>
    </provider>
    <provider id="android" label="Android" domain="android.com">
        <incoming uri="imap+ssl+://imap.gmail.com" username="$email"/>
        <outgoing uri="smtp+ssl+://smtp.gmail.com" username="$email"/>
    </provider>
 
 
    <!-- Common US providers -->
    
    <provider id="aim" label="AIM" domain="aim.com">
        <incoming uri="imap://imap.aim.com" label="IMAP" username="$email"/>
        <outgoing uri="smtp://smtp.aim.com:587" username="$email"/>
    </provider>
    <provider id="aol" label="AOL" domain="aol.com">
        <incoming uri="imap://imap.aol.com" label="IMAP" username="$email"/>
        <outgoing uri="smtp://smtp.aol.com:587" username="$email"/>
    </provider>
    <provider id="comcast" label="Comcast" domain="comcast.net">
        <incoming uri="pop3+ssl+://mail.comcast.net" username="$user"/>
        <outgoing uri="smtp+ssl+://smtp.comcast.net" username="$user"/>
    </provider>
    <provider id="compuserve" label="CompuServe" domain="cs.com">
        <incoming uri="imap://imap.cs.com" username="$user"/>
        <outgoing uri="smtp://smtp.cs.com" username="$user"/>
    </provider>
    <provider id="dotmac" label=".Mac" domain="mac.com">
        <incoming uri="imap+tls://mail.mac.com" username="$email"/>
        <outgoing uri="smtp+tls://smtp.mac.com" username="$email"/>
    </provider>
    <provider id="earthlink" label="Earthlink" domain="earthlink.net">
        <incoming uri="pop3://pop.earthlink.net" username="$email"/>
        <outgoing uri="smtp://smtpauth.earthlink.net:587" username="$email"/>
    </provider>
    <provider id="juno" label="Juno" domain="juno.com">
        <incoming uri="pop3://pop.juno.com" username="$user"/>
        <outgoing uri="smtp://smtp.juno.com" username="$user"/>
    </provider>
    <provider id="live" label="Windows Live Hotmail Plus" domain="live.com" note="@string/provider_note_live">
        <incoming uri="pop3+ssl+://pop3.live.com" username="$email"/>
        <outgoing uri="smtp+tls+://smtp.live.com" username="$email"/>
    </provider>
    <provider id="hotmail" label="Windows Live Hotmail Plus" domain="hotmail.com" note="@string/provider_note_live">
        <incoming uri="pop3+ssl+://pop3.live.com" username="$email"/>
        <outgoing uri="smtp+tls+://smtp.live.com" username="$email"/>
    </provider>
    <provider id="msn" label="Windows Live Hotmail Plus" domain="msn.com" note="@string/provider_note_live">
        <incoming uri="pop3+ssl+://pop3.live.com" username="$email"/>
        <outgoing uri="smtp+tls+://smtp.live.com" username="$email"/>
    </provider>
    <provider id="mobileme" label="MobileMe" domain="me.com">
        <incoming uri="imap+tls://mail.me.com" username="$email"/>
        <outgoing uri="smtp+tls://smtp.me.com" username="$email"/>
    </provider>
    <provider id="netzero" label="NetZero" domain="netzero.com">
        <incoming uri="pop3://pop.netzero.com" username="$user"/>
        <outgoing uri="smtp://smtp.netzero.com" username="$user"/>
    </provider>
    <provider id="sbcglobal" label="SBC Global" domain="sbcglobal.net">
        <incoming uri="pop3://pop.sbcglobal.yahoo.com" username="$email"/>
        <outgoing uri="smtp://smtp.sbcglobal.yahoo.com" username="$email"/>
    </provider>
    <provider id="verizon" label="Verizon" domain="verizon.net">
        <incoming uri="pop3://incoming.verizon.net" username="$user"/>
        <outgoing uri="smtp://outgoing.verizon.net" username="$user"/>
    </provider>
    <provider id="yahoo" label="Yahoo Plus" domain="yahoo.com" note="@string/provider_note_yahoo">
        <incoming uri="pop3+ssl+://plus.pop.mail.yahoo.com" username="$user"/>
        <outgoing uri="smtp+ssl+://plus.smtp.mail.yahoo.com" username="$user"/>
    </provider>
  
    <!-- Common UK providers -->
    
    <provider id="aol-uk" label="AOL" domain="aol.co.uk">
        <incoming uri="imap+ssl+://imap.uk.aol.com" label="IMAP" username="$user"/>
        <outgoing uri="smtp+ssl+://smtp.uk.aol.com" username="$user"/>
    </provider>
    <provider id="bt" label="BT Internet" domain="btinternet.com">
        <incoming uri="pop3://mail.btinternet.com" username="$email"/>
        <outgoing uri="smtp://mail.btinternet.com" username=""/>
    </provider>
    <provider id="tiscali" label="Tiscali" domain="tiscali.co.uk">
        <incoming uri="pop3://pop.tiscali.co.uk" username="$email"/>
        <outgoing uri="smtp://smtp.tiscali.co.uk" username="$email:wq"/>
    </provider>
    <provider id="yahoo-uk" label="Yahoo" domain="yahoo.co.uk" note="@string/provider_note_yahoo_uk">
        <incoming uri="pop3+ssl+://pop.mail.yahoo.co.uk" username="$user"/>
        <outgoing uri="smtp+ssl+://smtp.mail.yahoo.co.uk" username="$user"/>
    </provider>
    
    <!-- Common Germany providers -->
    
    <provider id="freenet" label="Freenet" domain="freenet.de">
        <incoming uri="pop3://mx.freenet.de" username="$user"/>
        <outgoing uri="smtp+ssl://mx.freenet.de" username="$email"/>
    </provider>
    <provider id="gmx" label="GMX" domain="gmx.de">
        <incoming uri="pop3+tls://pop.gmx.net" username="$email"/>
        <outgoing uri="smtp+tls://mail.gmx.net" username="$email"/>
    </provider>
    <provider id="T-Online" label="T-Online" domain="t-online.de" note="@string/provider_note_t_online">
        <incoming uri="pop3://popmail.t-online.de" username="$email"/>
        <outgoing uri="smtp://smtpmail.t-online.de" username="$email"/>
    </provider>
    <provider id="web.de" label="Web.de" domain="web.de">
        <incoming uri="pop3+tls://pop3.web.de" username="$user"/>
        <outgoing uri="smtp+tls://smtp.web.de" username="$user"/>
    </provider>
</providers>
```
As with all Android application resources, the platform will load alternate resources based on the platform configuration values. See Resources and Internationalization in the Android SDK for details. To configure email providers for a specific mobile network operator, place the customized providers in a separate providers.xml file and place it under a Mobile Network Code (MNO) specific resource folder. For example, Email/res/xml-mccXXX-mncYYY/providers.xml where XXX and YYY represent the three-digit MCC and two to three digit MNC values.


