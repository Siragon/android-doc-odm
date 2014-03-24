###Creating Release Keys and Signing Builds
####Introduction

Android requires that each application be signed with the developer's digital keys to enforce signature permissions and application request to use shared user ID or target process. For more information on the general Android security principles and signing requirements, see the Android Security and Permissions section in the Android Developer Guide). The core Android platform uses four keys to maintain security of core platform components:

   - **platform**: a key for packages that are part of the core platform.
   - **shared**: a key for things that are shared in the ```home/contacts process```.
   - **media**: a key for packages that are part of the ```media/download``` system.
   - **releasekey**: the default key to sign with if not otherwise specified

These keys are used to sign applications separately for release images and are not used by the Android build system. The build system signs packages with the testkeys provided in build/target/product/security/. Because the testkeys are part of the standard Android open source distribution, they should never be used for production devices. Instead, device manufacturers should generate their own private keys for shipping release builds.

####Request the keys
Síragon provide the private key and the passfrase by email.
Please contact [android@siragon.com.ve](mailto:android@siragon.com.ve)

####Signing a build for release
Signing a build for a release is a two-step process.

    1. Sign all the individual parts of the build.
    2. Put the parts back together into image files.
    
#####Signing applications
Use ```build/tools/releasetools/sign_target_files_apks``` to sign a ```target_files``` package. The ```target_files``` package isn't built by default, you need to make sure to specify the "dist" target when you call make. For example:

make -j4 PRODUCT-<product_name>-user dist

The command above creates a a file under ```out/dist``` called ```<product_name>-target_files.zip```. This is the file you need to pass to the ```sign_target_files_apks``` script.

You would typically run the script like this:
```text
./build/tools/releasetools/sign_target_files_apks -d vendor/siragon/security/<product_name> <product_name>-target_files.zip signed-target-files.zip
```
If you have prebuilt and pre-signed apk's in your build that you don't want re-signed, you must explicitly ignore them by adding ```-e Foo.apk=``` to the command line for each apk you wish to ignore.

```sign_target_files_apks``` also has many other options that could be useful for signing release builds. Run it with ```-h``` as the only option to see the full help.

#####Creating image files

Once you have signed-target-files.zip, create the images so you can put it onto a device with the command below:
```text
build/tools/releasetools/img_from_target_files signed-target-files.zip signed-img.zip
```
```signed-img.zip``` contains all the ```.img``` files. You can use ```fastboot update signed-img.zip``` to use fastboot to get them on the device.
