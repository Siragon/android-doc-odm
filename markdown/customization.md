###Customization
####Default wallpaper
The ```framework-res.apk``` contain the ```default_wallpaper.jpg```
```text
    /system/framework/framework-res.apk
    /res/drawable-nodpi/default_wallpaper.jpg
    /res/...-.../default_wallpaper.jpg
```
Check the size to select.

Click to download.

**960x800**

[![](/android-doc-odm/res/wallpapers/960x800/wallpaper1.thumbnail.jpg)](/android-doc-odm/res/wallpapers/960x800/wallpaper1.jpg)
[![](/android-doc-odm/res/wallpapers/960x800/wallpaper2.thumbnail.jpg)](/android-doc-odm/res/wallpapers/960x800/wallpaper2.jpg)
[![](/android-doc-odm/res/wallpapers/960x800/wallpaper3.thumbnail.jpg)](/android-doc-odm/res/wallpapers/960x800/wallpaper3.jpg)
[![](/android-doc-odm/res/wallpapers/960x800/wallpaper4.thumbnail.jpg)](/android-doc-odm/res/wallpapers/960x800/wallpaper4.jpg)
[![](/android-doc-odm/res/wallpapers/960x800/wallpaper5.thumbnail.jpg)](/android-doc-odm/res/wallpapers/960x800/wallpaper5.jpg)

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

###Bootloader Splashscreen Customization
The boot logo of the SoC when the kernel initialize.
Example to use SoC logo:

Mediatek:

![](/android-doc-odm/res/mediatek.jpg)

Allwinner A31:

![](/android-doc-odm/res/a31.jpg)

Note: Always use black background.

###Android Boot Screen Customization
At startup, Android displays a splashscreen image while booting the device. Do the following to modify the default splash screen:

Use splashscreen like this:

![](/android-doc-odm/res/boot_screen.png)

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
###Bootanimation

There is a file called bootanimation.zip stored in /system/media/ in the root file system (or system/customize/resource or data/local). This file contains two things:

1) A description file (desc.txt) that outlines how the animation progresses, what images to use, image size etc.

2) Folder(s) that contain the images for the animation.

The basic structure of the bootanimation.zip file is as follows:
```text
bootanimation.zip
|-- desc.txt
|-- part0
`-- part1
```

part0 and part1 are directories that contain a series of images for example, in part 0 there is:
```text
part0
|-- boot_00001.png
|-- boot_00002.png
|-- boot_00003.png
|-- boot_00004.png
|-- boot_00005.png
|-- boot_00006.png
|-- boot_00007.png
|-- boot_00008.png
|-- boot_00009.png
`-- boot_00010.png
```
And in part 1 there are:
```text
part1
|-- boot_00011.png
|-- boot_00012.png
|-- boot_00013.png
|-- boot_00014.png
|-- boot_00015.png
|-- boot_00016.png
|-- boot_00017.png
|-- boot_00018.png
|-- boot_00019.png
`-- boot_00020.png
```
These images form the 'part0' and 'part1' animations that are combined as outlined in the 'desc.txt' file to form the overall startup animation. The images are ordered by number and run in sequence.

The 'desc.txt' file outlines how the animation progresses and a sample is as follows:
```text
512 256 30
p 1 0 part0
p 0 0 part1
```
'523' is the width of the animation<br/>
'256' is the height of the animation<br/>
'30' is the desired fps of the animation<br/>
'p' defines a animation part<br/>
'1' how many times this animation part loops<br/>
'0' defines a pause (max 10)<br/>
'part0' is the folder name where the animation images are<br/>
'p' defines another animation part<br/>
'0' defines that it loops forever (until android starts)<br/>
'0' defines a pause<br/>
'part1' is the folder for the second animation part.

Config the makefile:
```makefile
PRODUCT_COPY_FILES += <path>/<filename>:system/media/bootanimation.zip
```

[Download bootanimation 480x854](/android-doc-odm/res/bootanimation.480x854.zip)

[Download bootanimation 540x960](/android-doc-odm/res/bootanimation.540x960.zip)

[Download bootanimation 1280x800](/android-doc-odm/res/bootanimation.1280x800.zip)

###Network Customization Platform
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

###Build-time APN configuration

To set the APN configuration for a particular product target, add an apns-conf.xml file to the product configuration (do not modify the default platform APNs). This allows multiple products, all with different APNs, to be built off the same code base.

To configure APNs at the product level, add a line to the product configuration file like the example below (vendor/siragon/products/myphone-us.mk):

```text
PRODUCT_COPY_FILES := vendor/siragon/etc/apns-conf-us.xml:system/etc/apns-conf.xml
```

[Download the file apns-conf.xml](/android-doc-odm/res/apns-conf.xml)

###APN configuration at run time
At runtime, the Android reads APNs from the following file:
```text 
system/etc/apns-conf.xml
```
Android supports the following run-time network configuration methods to choose the appropriate APN from the list of configured APNs:

**Automatic Configuration:** At boot time, Android determines the correct network configuration based on the MCC and MNC from the SIM card and automatically configure all network settings.

**Manual Configuration:** The platform will also support runtime (user) manual selection of network settings by name, for example, "Company Name US," and will support manual network configuration entry.

**WAP / SMS Push Configuration:** The network configurations are standard Android resources. You can upgrade a resource at runtime by installing a new system resource APK package. It will be possible to develop a network configuration service which listens to a specific binary SMS port for binary SMS messages containing the network configurations. NOTE: The implementation will likely be network operator dependent due to inconsistent SMS ports, binary SMS formats, etc.

###Customizing pre-loaded applications
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

###Customizing browser default homepage
Browser homepage are stored as string resources in the Browser application: //android/packages/apps/Browser/res/values/strings.xml. Homepage are defined as simple value string called "homepage_base". This might be changed to something like:

```xml
<string name="homepage_base" translatable="false"/>
 http://ve.yahoo.com?fr=appattach&amp;type=233
</string>
```

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


###Set the Default Search Engine
Set the default search provider to “yahoo”

The “default” search provider value is located in the Android Source file:
```text
/packages/apps/Browser/res/xml/advanced_preferences.xml
```

To specify Yahoo! as the default search engine, locate the ```SearchEnginePreference``` element and change the ```android:defaultValue``` attribute: ```android:defaultValue="yahoo"```

Additionally, in order to adjust any searches made before the settings have been used, edit the ```getSearchEngineName()``` method in the file:
```text
/packages/apps/Browser/src/com/android/browser/BrowserSettings.java
```

To specify Yahoo! as the default search engine, change the method to something like this:

```java
public String getSearchEngineName() { 
	return mPrefs.getString(PREF_SEARCH_ENGINE, "yahoo"); 
}
```
*Please note that “yahoo” is all lower case in both instances.
###Modify the Yahoo Search URL

In order to get credit for any searches sent to Yahoo!, you will need to edit the URL strings in this file:

```text
/packages/apps/Browser/res/values/all_search_engines.xml (or arrays.xml)
```

This file contains all the different URLs for Yahoo search in different countries, so you’ll need to edit as many of them as are relevant to countries where you’ll be shipping. In each case, replace the existing value:
```xml
<item>http://search.yahoo.com/search?ei={inputEncoding}&fr=crmas&p={searchTerms}</item>
```
with the values from your appAttach contract:

```xml
<item>http://ve.yhs4.search.yahoo.com/yhs/mobile/search?hspart=appattach&hsimp=yhsm-appattach&type=230&p={searchTerms}</item>
```
*Please note the usage of &amp; for the parameter separator.

*Not all regions in all_search_engines.xml have an appAttach URL asset. Please refer to the list of URLs provided by appAttach to know which regions are eligible for this offer.


###Email Provider Customization
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
 
 
    <!-- Common VE providers -->
    <!-- 
    ToDo
    https://mi.movistar.com.ve/ 
    @movistar.com.ve
    www.mipunto.com/autenticacion/autenticacion.jsp
    @telcel.net.ve
    http://mail.intercable.net.ve/
    @intercable.net.ve
    http://correo.cantv.net/
    @cantv.net.ve
    Pop.cantv.net
	Port: 110
	Mail.cantv.net
    Port: 465 ssl/tls
	Port: 25
    username@cantv.net
    -->
```
As with all Android application resources, the platform will load alternate resources based on the platform configuration values. See Resources and Internationalization in the Android SDK for details. To configure email providers for a specific mobile network operator, place the customized providers in a separate providers.xml file and place it under a Mobile Network Code (MNO) specific resource folder. For example, Email/res/xml-mccXXX-mncYYY/providers.xml where XXX and YYY represent the three-digit MCC and two to three digit MNC values.

###Change languages and regional settings

Need check the file ```languages_full.mk``` and ```locales_full.mk```
Many devices need change the file: ```/system/etc/language.cfg``` to add "Español (Venezuela)" and add this language by default in the ```build.prop```

```ini
ro.product.locale.language=es
ro.product.locale.region=VE
persist.sys.timezone=America/Caracas
ro.com.android.dateformat=MM-dd-yyyy
```

```text
es_VE "Español (Venezuela)"
es_AR "Español (Argentina)"
pt_BR "Português (Brasil)"
en_US "Inglés (Estados Unidos)"
ar_EG "Árabe (Egipto)"
```
Language files:
```text
/frameworks/base/core/res/res/values-es/arrays.xml
/frameworks/base/core/res/res/values-es/strings.xml
```
###Sounds

[Download ringtone](/android-doc-odm/res/Siragonringtone1.mp3)

[Download notification_sound](/android-doc-odm/res/SiragonSMS1.mp3)

[Download bootsound](/android-doc-odm/res/SiragonOn1.2.mp3)

```ini
ro.config.ringtone=Siragonringtone1.mp3
ro.config.ringtone_2=Siragonringtone1.mp3
ro.config.notification_sound=SiragonSMS1.mp3
```

###Bluetooth
Change the name of the bluetooth device in the ```build.prop```:
```ini
net.bt.name=Siragon
```
###Drivers USB

Provide the signed drivers for these USB clases:
```text
USB Composite Device
USB PID
MSC+ADB
MSC
MTP+ADB
MTP
RNDIS+ADB
RNDIS
HID
Fastboot
```
Other USB classes that vary depending on bootloader or SoC:
```text
FEL Mode
APX Mode
and others...
```
###Certificates

```text
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number: 11 (0xb)
        Signature Algorithm: sha256WithRSAEncryption
        Issuer: CN=Autoridad de Certificacion Raiz del Estado Venezolano, C=VE, L=Caracas, ST=Distrito Capital, O=Sistema Nacional de Certificacion Electronica, OU=Superintendencia de Servicios de Certificacion Electronica/emailAddress=acraiz@suscerte.gob.ve
        Validity
            Not Before: Dec 28 16:51:00 2010 GMT
            Not After : Dec 25 23:59:59 2020 GMT
        Subject: emailAddress=contacto@procert.net.ve, L=Chacao, ST=Miranda, OU=Proveedor de Certificados PROCERT, O=Sistema Nacional de Certificacion Electronica, C=VE, CN=PSCProcert
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
            RSA Public Key: (4096 bit)
                Modulus (4096 bit):
                    00:d5:b7:f4:a3:94:33:a1:46:a9:55:61:49:0d:a8:
                    87:73:5e:91:2d:70:c1:06:1a:94:da:3d:ec:15:42:
                    c1:f5:8c:ae:6a:17:f1:8a:ad:fc:80:95:ea:83:44:
                    a2:5b:7a:55:ce:4f:a7:a5:d5:ba:b8:1f:a0:27:c0:
                    50:53:3e:8d:b9:c0:0e:b8:15:dc:d6:6c:f8:9e:f8:
                    04:25:df:80:8f:10:85:dd:7d:2f:7b:80:dd:57:00:
                    64:23:f8:6e:c9:be:95:4f:e1:75:ec:e0:7e:5e:95:
                    cd:b1:ef:be:7a:42:d8:c9:2c:d3:eb:1a:1a:22:8b:
                    b7:7f:06:89:e5:3c:f5:12:c0:bb:d3:0b:99:5f:90:
                    7c:8e:2d:2f:77:33:92:4a:21:46:a8:a9:08:ac:f1:
                    f6:11:02:d9:95:16:9e:8d:2f:96:e6:02:dd:75:c2:
                    14:2a:5a:d6:c9:7d:25:c2:c1:fc:aa:67:85:e2:ec:
                    be:d1:7c:3c:fa:af:d5:6e:ff:53:41:d4:f5:32:38:
                    b1:e2:5f:c4:f9:8e:10:ef:06:a9:02:89:ff:e3:0c:
                    6e:97:e0:df:9d:db:21:d0:f4:3e:08:69:6c:d8:d4:
                    e4:36:f8:83:b6:b2:36:8f:9c:ef:3a:37:16:7d:bf:
                    a2:69:d7:3b:5b:72:d0:af:aa:3f:5c:66:93:ac:0a:
                    22:61:b6:d2:a0:99:c8:54:93:5d:a8:b6:d1:bd:5d:
                    0a:5e:77:94:a2:2d:c0:82:8e:bc:ca:03:2a:34:ae:
                    73:f1:d4:b5:0c:bd:be:67:9b:54:eb:e1:fa:a0:5a:
                    ec:38:7e:3e:c1:cc:a2:c7:44:31:75:ea:3f:e5:07:
                    d2:ab:a1:25:96:f6:e6:e4:a0:5d:37:18:39:61:00:
                    33:5d:46:d4:00:c4:b4:ca:3c:f1:a2:a3:3e:f3:3a:
                    ff:69:30:2e:40:dd:f6:9f:9c:26:c9:96:37:ad:e7:
                    39:a2:bf:ea:69:db:55:22:95:53:2a:94:b5:df:ad:
                    16:38:81:75:66:e3:c7:2c:1b:93:9c:aa:8c:a3:ca:
                    d9:6c:3c:17:6d:9c:dc:7c:53:e0:20:27:43:36:f9:
                    12:e1:3c:5c:bd:66:bf:a2:69:23:38:b8:99:60:99:
                    0e:56:53:3a:9c:7e:14:8c:b0:06:6f:f1:86:76:90:
                    af:fd:af:fe:90:c6:8f:9f:7f:8b:92:23:9c:e7:15:
                    76:8f:d5:8b:94:13:72:69:fb:2b:61:63:88:ef:e6:
                    a4:5e:e6:a3:17:6a:58:47:cb:71:4f:14:0b:5e:c8:
                    02:08:26:a2:cb:e9:af:6b:8a:19:c7:cb:14:56:f5:
                    e1:da:b5:d9:fc:bf:73:38:da:f9:e7:af:6e:a4:37:
                    e2:07:27
                Exponent: 65537 (0x10001)
        X509v3 extensions:
            X509v3 Basic Constraints: critical
                CA:TRUE, pathlen:1
            X509v3 Issuer Alternative Name:
                DNS:suscerte.gob.ve, othername:<unsupported>
            X509v3 Subject Key Identifier:
                41:0F:19:38:AA:99:7F:42:0B:A4:D7:27:98:54:A2:17:4C:2D:51:54
            X509v3 Authority Key Identifier:
                keyid:AD:BB:22:1D:C6:E0:D2:01:A8:FD:76:50:52:93:ED:98:C1:4D:AE:D3
                DirName:/CN=Autoridad de Certificacion Raiz del Estado Venezolano/C=VE/L=Caracas/ST=Distrito Capital/O=Sistema Nacional de Certificacion Electronica/OU=Superintendencia de Servicios de Certificacion Electronica/emailAddress=acraiz@suscerte.gob.ve
                serial:0A
            X509v3 Key Usage: critical
                Certificate Sign, CRL Sign
            X509v3 Subject Alternative Name:
                DNS:procert.net.ve, othername:<unsupported>, othername:<unsupported>
            X509v3 CRL Distribution Points:
                URI:http://www.suscerte.gob.ve/lcr/CERTIFICADO-RAIZ-SHA384CRLDER.crl
                URI:ldap://acraiz.suscerte.gob.ve
            Authority Information Access:
                OCSP - URI:http://ocsp.suscerte.gob.ve
            X509v3 Certificate Policies:
                Policy: 2.16.862.3.1.2
                  CPS: http://www.suscerte.gob.ve/dpc
    Signature Algorithm: sha256WithRSAEncryption
        2b:59:eb:22:99:bb:84:aa:4f:de:90:c6:d1:86:71:23:9e:4b:
        03:91:47:70:bb:c0:92:60:ec:e0:d4:e7:6d:c6:d3:ed:67:83:
        77:52:d5:f2:e5:77:a7:36:b2:e3:54:be:d9:bb:0a:9b:11:ef:
        61:f4:c6:99:33:99:f5:af:00:39:8d:83:bf:a6:bd:35:7e:2c:
        5c:31:34:6f:6c:db:f3:64:01:98:aa:94:2c:41:dd:15:86:ca:
        6b:29:4e:16:c0:49:fc:d7:83:48:13:07:51:84:31:52:88:bb:
        86:17:c7:6b:2f:8a:20:ad:c5:0b:8f:70:3e:2a:bb:1b:71:8f:
        b9:a4:a0:fd:d8:95:d9:af:59:bf:25:2b:98:e9:63:93:2f:60:
        1e:c4:aa:f8:77:f5:8b:6c:2f:ed:7e:2e:b5:4f:40:0d:ee:bc:
        57:77:e7:d9:b6:d4:3f:95:27:3a:20:d5:e5:ae:ab:6c:35:9f:
        c1:a1:1d:59:dc:84:81:ee:4d:07:e2:48:b6:9e:4b:95:2d:41:
        b1:e1:e8:de:7e:2f:05:1e:68:ee:bf:bb:90:65:3a:c8:ee:ea:
        b1:18:37:1c:62:93:a4:a0:31:ec:71:6c:91:e6:a4:79:89:5a:
        14:a7:14:50:05:4c:a4:00:57:30:2c:c1:b5:61:96:dc:3e:1e:
        84:af:39:42:cf:e5:d0:2c:b1:24:bc:df:40:c3:ed:7f:63:4a:
        bd:e1:4f:12:64:86:95:f3:b0:e7:c8:b7:e1:53:bd:92:e6:f3:
        0c:96:b9:eb:e8:e6:92:ed:a7:81:09:14:0b:fc:95:7a:cf:8f:
        d6:34:4f:36:12:dc:5e:d1:34:75:c6:46:80:2f:95:04:8c:c7:
        86:c4:a8:26:89:a8:3f:19:9b:81:bb:51:a4:4a:86:ab:0b:11:
        0f:b1:ae:63:53:6d:28:ea:dd:33:56:38:1c:b2:ad:80:d3:d7:
        72:bd:9a:6c:99:63:e8:00:bb:41:76:05:b7:5b:99:18:8a:c3:
        b8:12:5c:56:cf:56:0c:7d:e8:e2:cf:ed:bc:74:47:fb:ee:d3:
        17:4e:22:4f:56:ff:50:f3:2e:e6:39:a6:82:d6:71:ca:de:b7:
        d5:ba:68:08:ed:99:cc:fd:a2:92:cb:69:b8:9d:f9:0a:a4:a6:
        3e:4f:93:28:2a:61:6c:07:26:00:ff:96:5f:68:86:b8:b8:ce:
        ca:55:e0:ab:b1:3d:7f:98:d7:33:0e:5a:3d:d8:78:c2:c4:60:
        2f:c7:62:f0:61:91:d2:38:b0:f6:9e:55:db:40:80:05:12:33:
        ce:1d:92:9b:d1:69:b3:ff:bf:f1:92:0a:61:35:3f:dd:fe:86:
        f4:bc:e0:1a:71:b3:62:a6
```
