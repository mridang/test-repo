# Mage FAQ

### How does Nosto treat tax settings?

As of version 2.10.3 Nosto extension tags the products according to the store's Price Display Settings \(see screenshot\) below. ![configuration\_\_\_settings\_\_\_stores\_\_\_magento\_admin](https://user-images.githubusercontent.com/15191701/40839884-0825538c-65ad-11e8-9e77-14445b42b877.png)

If the value of this setting is "Including Tax" Nosto will use the prices with taxes. If the value is "Excluding Tax" or "Including and Excluding Tax" Nosto will use prices without taxes.

### How do I enable or disable multi-currency?

See article about \[Multi Currency \(Exchange Rates\)\]\([https://github.com/Nosto/nosto-magento2/wiki/Multi-Currency-\(Exchange-Rates](https://github.com/Nosto/nosto-magento2/wiki/Multi-Currency-%28Exchange-Rates)\)\)

### How to improve order confirmation performance?

Please follow the following steps: 1. Update to latest nosto version: [https://github.com/Nosto/nosto-magento2/releases](https://github.com/Nosto/nosto-magento2/releases) 2. Setup cron job for magento. [http://devdocs.magento.com/guides/v2.1/config-guide/cli/config-cli-subcommands-cron.html](http://devdocs.magento.com/guides/v2.1/config-guide/cli/config-cli-subcommands-cron.html) 3. Change nosto indexer mode to Update by schedule. All indexers and their mode \(including Nosto indexer\) can be found from store admin “System” &gt; “Index management”. [https://user-images.githubusercontent.com/15191701/29363535-0f27b212-8299-11e7-9f31-ff9b5dd9a922.png](https://user-images.githubusercontent.com/15191701/29363535-0f27b212-8299-11e7-9f31-ff9b5dd9a922.png)

That improves the order confirmation performance and backend operation performance. But please make sure the magento cron job is running properly, otherwise nosto product information will not be updated to nosto in time.

### How do I remove the `___store` parameter from the URLs?

In order to remove the `___store` parameter, you will need to enable clean-urls in the advanced configuration. Please see the [URL Options](https://github.com/Nosto/nosto-magento2/wiki/Configuring#url-options) section in our configuration guide.

### Why is incomplete / cancelled order attributed to Nosto

Nosto's Magento extension send information about an order to Nosto via tagging and via API. Order is sent over the API to Nosto whenever an order \(`Magento\Sales\Model\Order`\) is saved in Magento 2. The definition of the observer can be [from here](https://github.com/Nosto/nosto-magento2/blob/master/etc/events.xml#L40-L42). This means that order data gets sent to Nosto when the order is created or updated regardless of the status of the order. Nosto has pre-defined set of order statuses that are automatically ignored \(cancelled, rejected, etc.\). If the initial order status or order updates sent within 30 minutes of the purchase don't have status that is considered ignored the orders will be treated as valid in Nosto.

If a merchant provides a possibility for offline payments \(cash on delivery, invoice, cheque, etc.\) or 3rd party payment gateways that do not redirect back to the store Nosto has no way of knowing if the payment has been fulfilled or not. These orders are also considered as valid unless they are cancelled within that 30 minutes window.

More info about the attribution can be found from [here \(Nosto's payment terms\)](http://www.nosto.com/payment-terms/)

