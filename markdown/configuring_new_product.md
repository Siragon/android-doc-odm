###Configuring a New Product

####Detailed Instructions
ToDo

####Product Definition Files
Product-specific variables are defined in product definition files. A product definition file can inherit from other product definition files, thus reducing the need to copy and simplifying maintenance.

Variables maintained in a product definition files include:

```PRODUCT_NAME``` use ```SP-``` for SmartPhones and ```TB-``` for Tablets <br/>
```PRODUCT_MANUFACTURER``` and ```PRODUCT_BRAND``` use Siragon without "í" <br/>
```PRODUCT_LOCALES``` for es_VE use es_ES and rename.

```Makefile
$(call inherit-product, build/target/product/generic.mk)

#Overrides
PRODUCT_NAME := SP-5110
PRODUCT_MANUFACTURER := Siragon
PRODUCT_BRAND := Siragon
PRODUCT_LOCALES := es_VE es_AR pt_BR en_US ar_EG
PRODUCT_PACKAGE_OVERLAYS := vendor/siragon/overlay
```