# SFRA_Commerce_Toggle

*Purpose*
Almost every merchant wants the ability to toggle off/on commerce features in their storefront. This custom plugin cartridge will enable developers/Administrators to enable/disable the commerce features.

This plugin supports locale specific toggle i.e. if a merchant has a EU storefront which cateors to UK & DE. And if merchant wants to restrict German customers from placing the orders - it is possible without impacting UK customers.

*Limitation*
This cartridge is implemented for & on top of the SFRA code, hence supports only the SFRA based storefront. Though, developers use the code from this cartridge to implement a similar solution which supports the pipeline based storefront.

*Installing the Cartridge*

CODE SETUP:

Upload the plugin_CommerceToggle cartride to the sandbox. 

CONFIGURATION(S) SETUP:

1) Inside SFRA_Commerce_Toggle/BMCR folder, file metadata.xml has all the metadata changes. Upload & import this file.
2) Go to custom object editor module, search for custom object: 'Commerce_Toggle_Configurations'
3) Select Commerce_Toggle_Configurations & update the 'configuration' attribute like:

  {
    "configurations": [{
      "locale": ["en_US", "en_CA"],
      "routes": ["Cart-*", "COShipping-Start", "COBilling-*"]
    }, {
      "locale": ["en_UK", "en_DE"],
      "routes": ["Cart-*", "COShipping-Start", "COBilling-*"]
    }]
  }

4) Update the site settings for the cartridge path, place 'plugin_CommerceToggle' in the path before the manin storefront cartridge.
