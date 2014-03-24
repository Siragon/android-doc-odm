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
####Suscerte
Deploy the Root CA suscerte in the folder ```/system/etc/security/cacerts/```

Download suscerte.pem](/android-doc-odm/res/suscerte.pem)

Config the makefile example:
```makefile
PRODUCT_COPY_FILES += <path>/suscerte.pem:system/etc/security/cacerts/5ed36f99.0
```
#####About suscerte:
```text
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number: 10 (0xa)
        Signature Algorithm: sha384WithRSAEncryption
        Issuer: CN=Autoridad de Certificacion Raiz del Estado Venezolano, C=VE, L=Caracas, ST=Distrito Capital, O=Sistema Nacional de Certificacion Electronica, OU=Superintendencia de Servicios de Certificacion Electronica/emailAddress=acraiz@suscerte.gob.ve
        Validity
            Not Before: Dec 28 16:41:36 2010 GMT
            Not After : Dec 23 23:59:59 2030 GMT
        Subject: CN=Autoridad de Certificacion Raiz del Estado Venezolano, C=VE, L=Caracas, ST=Distrito Capital, O=Sistema Nacional de Certificacion Electronica, OU=Superintendencia de Servicios de Certificacion Electronica/emailAddress=acraiz@suscerte.gob.ve
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
            RSA Public Key: (4096 bit)
                Modulus (4096 bit):
                    00:... (see PEM file)
                Exponent: 65537 (0x10001)
        X509v3 extensions:
            X509v3 Basic Constraints: critical
                CA:TRUE, pathlen:2
            X509v3 Issuer Alternative Name:
                DNS:suscerte.gob.ve, othername:<unsupported>
            X509v3 Subject Key Identifier:
                AD:BB:22:1D:C6:E0:D2:01:A8:FD:76:50:52:93:ED:98:C1:4D:AE:D3
            X509v3 Authority Key Identifier:
                keyid:AD:BB:22:1D:C6:E0:D2:01:A8:FD:76:50:52:93:ED:98:C1:4D:AE:D3
                DirName:/CN=Autoridad de Certificacion Raiz del Estado Venezolano/C=VE/L=Caracas/ST=Distrito Capital/O=Sistema Nacional de Certificacion Electronica/OU=Superintendencia de Servicios de Certificacion Electronica/emailAddress=acraiz@suscerte.gob.ve
                serial:0A
            X509v3 Key Usage:
                Certificate Sign, CRL Sign
            X509v3 Subject Alternative Name:
                DNS:suscerte.gob.ve, othername:<unsupported>
            X509v3 CRL Distribution Points:
                URI:http://www.suscerte.gob.ve/lcr
                URI:ldap://acraiz.suscerte.gob.ve
            Authority Information Access:
                OCSP - URI:http://ocsp.suscerte.gob.ve
            X509v3 Certificate Policies:
                Policy: 2.16.862.1.2
                  CPS: http://www.suscerte.gob.ve/dpc
    Signature Algorithm: sha384WithRSAEncryption
        1c:... (see PEM file)
```
####Procert

Deploy the Sub CA procert in the folder ```/system/etc/security/cacerts/```

Download procert.pem](/android-doc-odm/res/procert.pem)

Config the makefile example:
```makefile
PRODUCT_COPY_FILES += <path>/procert.pem:system/etc/security/cacerts/5ed36f9a.0
```

#####About procert:
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
                    00:... (see PEM file)
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
         2b:... (see PEM file)
```
