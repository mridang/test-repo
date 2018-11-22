# Mage FAQ

The extension can be configured by navigating to Stores &gt; Configuration &gt; Services &gt; Nosto.

### Image Options

This option determines which of the Magento image types is to be used for the product images in Nosto. By default, it is the "Base Image".

![image](https://user-images.githubusercontent.com/2778820/44143465-6f28b780-a08c-11e8-983f-a530a50e08a7.png)

This panel has tree image version to choose from:

* **Base Image**: The base image is the image version used as the main image on the product detail page.
* **Small Image**: The small image is the image version used as in the product listings such as category pages and search results.
* **Thumbnail**: The thumbnail is the image version used as the small image in shopping carts such the cart page or sidebar cart implementations

**Remove /pub/ from product images URLs** 

Set this to yes if you have configured the docroot to point to "pub/" directory.

### URL Options

This option removes the trailing `___store` parameter from the product URLs. If you have only a single-store view or would like to enable clean URLs, this can be toggled on.

![](https://user-images.githubusercontent.com/327432/36792597-a1591262-1ca3-11e8-812a-6a5dcdf096b3.png)

### Other Options

The other-attributes section can be used to map custom attributes to the certain Nosto fields. Magento does not have predefined fields for the brand, the GTIN or the supplier cost fields and these can be customised by the retailer.

![screen shot 2017-11-02 at 15 21 38](https://user-images.githubusercontent.com/327432/32328131-a34054e2-bfe1-11e7-881f-d8d2c3b58d73.png)

### Feature Flags

The feature-flags section can be used to toggle on/off different features. Certain features have a noticeable performance impact and you may need to toggle them off if you aren't leveraging the feature.

![screen shot 2018-04-11 at 16 13 13](https://user-images.githubusercontent.com/2778820/38618795-4c7950d8-3da3-11e8-999b-c65fdcc348c8.png)

**Send Customer Data To Nosto**

This option allow the merchant to enable/disable the sending of customer data to Nosto. If this option is disabled no customer tagging is done by Nosto.

#### Enable custom fields

![image](https://user-images.githubusercontent.com/2778820/44519745-9bafc500-a6d6-11e8-91a0-5726b3601280.png)

This option comes enabled by default. In case the merchant wants to completely hide, including from the page source code, he can disable using this feature flag.

### Attributes To Tags

The `attributes to tags` section can be used to add certain product attributes into the tags field of the product tagging. Doing so, will allow those properties to be used when building a recommendation template.   
 You can select multiple attributes holding control key.

![image](https://user-images.githubusercontent.com/2778820/42555072-be4025be-84ef-11e8-91df-e4328277f2fa.png)

### Currency Setup

If you store view make use of Magento's exchange rates, you may select `Exchange rates` option on the dropdown menu.   
 In case the store view uses only one currency, you may set this value to `Single currency`.   
 The `Disabled` option will prevent Nosto to do any currency conversion. This option should be used if you have a custom pricing handling setup.

![image](https://user-images.githubusercontent.com/2778820/42555862-4a901824-84f2-11e8-8105-c7a92bf1c25d.png)

