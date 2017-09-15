---
layout: default
group: release-notes
subgroup: 2.2.0 Release Candidate
title: Magento Commerce 2.2 Release Candidate 3 Release Notes
menu_title: Magento Commerce 2.2 Release Candidate 3 Release Notes
menu_order: 480
level3_menu_node:
level3_subgroup:
github_link: release-notes/release-notes-2-2-RC3-EE.md
---

*	TOC
{:toc}


*Release date: September 12, 2017*

*Notes updated: September 12, 2017*




Magento Commerce 2.2.0 Release Candidate 3x (formerly Enterprise Edition) includes significant new features as well as many bug fixes.

Looking for information about how the Magento 2.2.0 Release Candidate evaluation program works? Check out the [Magento 2.2.0 Release Candidate QuickStart Guide]({{page.baseurl}}release-notes/release-candidate/quick-start.html) for more information. This guide provides a handy overview of [Component Status]({{page.baseurl}}release-notes/release-candidate/component-status.html), too.



## Highlights

Magento Enterprise Edition 2.2.0 Release Candidate 3 includes substantial new features as well as many bug fixes. Look for the following highlights in this release:

* **Enhanced B2B feature set** removes points of friction from the B2B purchasing process. We reduce the cost and complexity of building a B2B site on Magento by providing company account management features out-of-the-box.  B2B companies can easily view and manage all of their quotes in the Magento Admin Panel. B2B APIs enable backend integrations, too. Read more about Magento B2B in the [B2B Developer Guide]({{page.baseurl}}b2b/bk-b2b.html).


* **Signifyd fraud protection** is now integrated with Magento. Signifyd identifies and rejects potential fraudulent orders and provides
100% chargeback protection. We provide an introduction to Signifyd integration with Magento [here]({{page.baseurl}}mrg/ee/Signifyd.html).



* **Significant enhancements in platform security and developer experience**. Security improvements include the removal of specific un-serialize calls and changes to hashing algorithm to improve security for sensitive values. Developers will appreciate  improvements in debugging, customizations, and logging. We've introduced **Mass Asynchronous Operations as a framework feature** that leverages our queueing system to provide increased scalability for long running business processes.



* **Upgraded technology stack.** Magento has dropped support for PHP 5.6 and Varnish 3.  We now support PHP 7.1, along with Redis 3.2, MySQL 5.7, Varnish 5 support. All third-party libraries have been upgraded to the latest stable version.


* **Pipeline deployment**, a new deployment process, enables separate build and deployment stages that can run separately. Resource-intensive processes can run on the build server. Pipeline deployment supports easy management of configuration between environments, too. Read more about pipleine deployment [here]({{page.baseurl}}config-guide/deployment/pipeline/).


* **Substantial performance gains from improvements in indexing, cart, and cache operations**. Customers can browse and shop on a storefront while indexers are running. (Long-running indexers operate in batches to better manage memory and run times.) Cart improvements enable a
buyer to create a cart with more than 300 line items, and merchants can process a cart with at least 300 line items.



## Issues fixed in Release Candidate (RC 2x)
The following fixed and open issues have been logged against the Magento 2.2.0 RC2x release. Issues fixed in the  Release Candidate 1.x are listed below. 


### Installation, configuration, and deployment

<!--- 70705 -->* The installation process no longer stops when loading the `Magento_Tax` module. [GitHub-10138](https://github.com/magento/magento2/issues/10138) (RC2.0)

<!--- 70571 -->* You can now activate DEBUG logging while running Magento in production mode. (This feature is available, but disabled by default.) (RC21)

<!--- 71257 -->* The ability to disable module output has been removed from Admin. If you disabled module output from Admin in a previous release, you must manually configure these settings. See [Disable module output]({{page.baseurl}}config-guide/config/disable-module-output.html) for details. (RC21)


<!--- 70516 -->* Magento no longer indicates errors when you install without AMQP. Previously, Magento displayed the following error: (RC21)

	`report.CRITICAL: Error Connecting to server (0): Failed to parse address ":" {"exception":"[object] (PhpAmqpLib\\Exception\\AMQPRuntimeException(code: 0): Error Connecting to server (0): Failed to parse address \":\" at /vendor/php-amqplib/php-amqplib/PhpAmqpLib/Wire/IO/StreamIO.php:106)"} []`


<!--- 70573 -->* It is now possible to configure Redis settings for session storage, default cache, and full page cache from the command line. (RC22)


<!--- 64351 -->* Magento now correctly generates URL rewrites when you save a product. (RC22)


<!--- 67037 -->* The `core_config_data.value` of the `core_config_data` table is now populated consistently when you upgrade to or freshly install  Magento 2.2. (RC23)


<!--- 67092 -->* The `salesrule_product_attribute` table is now populated consistently when you upgrade to or freshly install  Magento 2.2. (RC23)

<!--- 71551 -->* Inconsistencies in the database tables that contain quote information no longer result when you upgrade from Magento 2.1.8 to 2.2. (RC23)

<!--- 71890 -->* Magento no longer throws an exception when the configuration checksum is absent on a new installation. (RC30) 





### Cart

<!--- 70806 -->* The Persistent Shopping Cart feature now works as expected when enabled. This feature (**Store > Configurations > CUSTOMERS > Persistent Shopping Cart > General Options > Enable Persistence = Yes**) persists information about viewing, comparison, wish list and last ordered items under a long-term cookie. (RC21)



### Catalog

<!--- 69717 -->* Custom option IDs no longer change during import. Previously, custom option ID values were deleted, and new values were added. (RC2.0)

<!--- 70877 -->* You can now successfully add a product to the compare list. Previously, when you tried to add a product to a compare list, Magento displayed an error. (RC2.0)

<!--- 67618 -->* View permissions to high-level product categories now work as expected. Previously,  a user restricted to browse a category could still see the category in the top-level navigation menu if the page were previously cached in FPC. (RC2.0)

<!--- 70750 -->* Magento now displays an accurate view of high-level product categories based on viewer permission. Previously, Magento displayed only the product categories that users who belonged to the NOT_LOGGED_IN customer group were permitted to view, no matter which user logged in. (RC2.0)


<!--- 71242 -->* We’ve resolved failures with indexing in installations that implemented catalogs containing at least 5,000 - 6,000 SKUs. (RC21)


<!--- 70619 -->* You can now successfully filter category products using the scope selector. (RC21)

<!--- 69967 -->* Magento no longer indexes configurable products multiple times. Previously,  when you enabled break point activation on a configurable product, configurable products were indexed twice. (RC22)

<!--- 70987 -->* Magento no longer displays an error when you open a product with a Fixed Product Tax attribute enabled. (RC22)

<!--- 61018 -->*  You can now use REST to add video to a product. [GitHub-7153](https://github.com/magento/magento2/issues/7153) (RC30)




### Configurable products

<!--- 70346 -->* Magento no longer displays a configurable product on the storefront when its child products are deleted and the **Display Out of Stock Products** setting is set to **No**. (RC30)

<!--- 71656 -->* Configurable products no longer show up on category page when all children are set to **enable product = No** and **display out-of-stock products = Off**. (RC30)



### Checkout

<!--- 70846 -->* Magento now displays white space after the first address field of the customer address field during checkout. (RC21)


### Elasticsearch

<!--- 71562 -->* The Elasticsearch indexer search-by-attribute functionality now works as expected. (RC23)


### Email

<!--- 71349 -->* You can now configure an email return-path. (RC21)

<!--- 65631 -->* Magento now sends email that provides updates on the status of RMA authorization. (RC21)





### Gift wrap

<!--- 70603 -->* You can now add gift options to an order if logged in using a secure URL. (RC23)


### Import and Export

<!--- 60470 -->* Magento now successfully saves products with imported options. (RC22)

<!--- 71013 -->* The export process now populates values in the  `configurable variations` column for configurable products  as expected. Previously, when exporting more than one product, the values for the `configurable variations` column for configurable products were not included. (RC23)



### Miscellaneous

<!--- 64047 -->* A null value may now be specified to unset the special_price attribute. (RC2.0)

<!--- 70642 -->* You can upload a new logo (or change other display features) when editing a transactional email. Previously, Magento displayed an error after you tried to save changes you may have made to this feature. (RC2.0)

<!--- 71180 -->* Customers can now place orders as expected when Magento is running a French locale in production mode. Previously, customers could not complete a transaction in a storefront running a French locale, although they could if they switched to the storefront running the English locale. (RC2.0)

<!--- 71173 -->* You can now enable JavaScript minification without error. Previously, after enabling JS minification, the Magento  Admin displayed 404 errors when accessing JavaScript elements. (RC2.0)


<!--- 70517 -->* You can now successfully check out when the **Deferred Stock Update** option is enabled, and the AMQP connection is not configured. Previously, checkout failed, and Magento displayed this message: 
`Error Connecting to server (0): Failed to parse address ":" {"exception":"[object](PhpAmqpLib\\Exception\\AMQPRuntimeException(code: 0): Error Connecting to server (0): Failed to parse address \":\" at vendor/php-amqplib/php-amqplib/PhpAmqpLib/Wire/IO/StreamIO.php:106)"}` (RC2.0)

<!--- 70816 -->* The WSDL listing now lists all available methods at all times without requiring authorization. (RC21)

<!--- 71030 -->* Magento now plays the sound from only the video you’ve selected. Previously, when you clicked on a video associated with a configurable product, Magento played the soundtrack from both the selected video and the video of its parent. (RC21)

<!--- 71434 -->* Varnish now caches pages with `.html` extensions. (RC21)

<!--- 69757 -->* Magento now displays uncorrupted information in the shared catalogs  bulk operations  report. Previously, error information was corrupted. (RC21)

<!--- 70853 -->* We’ve fixed an SQL error that previously caused a logical error during the creation of a TargetRule. (This issue affected the `modifyConditionByCategoryIdsAttribute` function.) (RC21)

<!--- 71179 -->* Customers who subscribe to a newsletter are now subscribed as expected after confirming their account. Previously, Magento unsubscribed customers from the newsletter after confirming their account. 

<!--- 71230 -->* The Firefox browser now correctly displays the Hierarchy Tree in **Admin Panel > Content > Hierarchy**.  (RC22)


<!--- 70540 -->* You can now successfully edit bundle product options from the shopping cart. Previously, when you selected a bundle product in the cart, Magento displayed the product edit page, but you could not change the bundle option. (RC23)

<!--- 64085 -->* Fixed HTML inline style used when sending emails that implement the upgraded `emorgifier` library. [GitHub-8241](https://github.com/magento/magento2/issues/8241) (RC23)

<!--- 71415 -->* Mass actions now work as expected on the Customer grid. Previously, Magento could not process more than 20 items at a time. (RC23)

<!--- 70377 -->* Magento now correctly calculates the tier price percentage when displayed prices include tax. [GitHub-8833](https://github.com/magento/magento2/issues/8833)(RC30)

<!--- 72112 -->*  Subcategories no longer show up in the menu when the parent category is disabled or hidden from the menu. [GitHub-10064](https://github.com/magento/magento2/issues/10664)(RC30)

<!--- 59810 -->* Showing reports on the **Reports > Coupons** page no longer throws an error when the user is in a non-default Admin locale. [GitHub-7037](https://github.com/magento/magento2/issues/7037) (RC30)


### Payment methods

<!--- 70500 -->* Fixed issue related to incorrect stock quantity calculation for bundle and configurable products during the place order flow with PayPal Express Checkout. (RC22)

<!--- 71307 -->* Paypal errors no longer occur when Fixed Product Tax  (FPT) is enabled. Previously,  when a product had an FPT, Paypal Express reported an error when you tried to place the order. (RC22)

<!--- 71371 -->* Merchants can now accept payment on a Suspected Fraud order without Magento altering the amount in Total Paid. Previously,  when a merchant accepted payment for an order with a  status  of Suspected Fraud, Magento doubled the payment amount. (RC22)

<!--- 71050 -->* Magento now completes processing an order if the customer needs to re-enter credit card information during the order process. Previously, Magento returned this error `No such entity with customerId = 0`. (RC22)


### Reports

<!--- 69757 -->* Magento now displays uncorrupted information in the shared catalogs bulk operations report. Previously, error information was corrupted. (RC23)



### Shipping

<!--- 72305 -->* We’ve added support for the change to the USPS API that USPS implemented on September 1, 2017. After installing or upgrading to this release, Magento will display the Domestic rate for USPS, First-Class Mail Parcel as expected. Previously, the USPS First-Class Mail Parcel option was not available after September 1, 2017 on installations running Magento 2.x unless you applied the workaround described [here](http://devdocs.magento.com/guides/v2.1/release-notes/tech_bull_USPS-patch-Sept2017.html). (RC30)


<!--- 67283 -->* When upgrading Magento from 2.1.x to 2.2, the `quote_address.free_shipping` column is the same whether you upgraded from a previous installation of Magento or performed a fresh installation. Previously, different upgrade/installation options affected the contents of this column. (RC2.0)

<!--- 70861-->* Errors in shipping rates no longer occur when a customer changes the country during guest checkout and DHL is enabled. Previously, a customer changing country during guest checkout resulted in inaccurate shipping rates. (RC2.0)

<!--- 71749-->* Magento now displays tracking information when selected for the second shipping label created for the DHL shipping method. Previously, when you tried to display a completed DHL  shipping label, Magento displayed an exception. (RC23)


### Staging

<!--- 70671 -->*  You can now preview an update from the dashboard and click on links and see how the entire instance would look like for a store between some dates. Previously, the links from the Preview page were broken. (RC2.0)

<!--- 70708 -->* You can now change the Start Date for a campaign. (RC2.0)

<!--- 71373 -->* You can now install Magento Commerce without Staging modules. (RC21)

<!--- 71289 -->* Magento now saves scheduled updates for products with custom options as expected. (RC22)

<!--- 71708 -->* You can now create a staging update for a product that contains a unique attribute in its attribute set. Previously, under these conditions, Magento displayed this error: `The value of attribute "test" must be unique’`. (RC23)

<!--- 71215 -->* Magento no longer creates extraneous database values when you schedule new Staging updates. (RC30)


### URL rewrites

<!--- 70663 -->* You can now assign products to a category when **Match Products by rule** is enabled. (RC2.0)

<!--- 70779 -->* Magento now saves Category URL rewrites as expected. (RC2.0)




## Issues resolved in Release Candidate 1.x

### Installation and Configuration 

<!--- 69675 -->* We’ve fixed problems with the upgrade process from 2.1.7 EE to 2.2.0 EE. (RC1.6)


<!--- 69854 -->* You can now successfully use the `config:set` command to set allowed or default currencies. 


<!--- 67299, 67315 -->* The `catalog_url_rewrite_product_category` table is the same whether you’ve freshly installed or updated Magento 2.2. 


<!--- 70314 -->* The `cron:install` command now works as expected in Magento 2.2.0 RC1.x. Previously, the configuration for `crontab` commands contained double quotes that were not escaped, which caused invalid commands to be written to the `crontab` file. [GitHub-10040](https://github.com/magento/magento2/issues/10040)


<!--- 70318 -->* You can now generate static content without a database connection. [GitHub-10041](https://github.com/magento/magento2/issues/10041) (RC1.5) 

<!--- 67020 -->* Magento now handles the `catalog_product_entity_media_gallery_value.position`  value the same whether you’ve installed or upgraded the product. Previously, these values differed depending upon whether you upgraded or freshly installed your Magento code. (RC1.5)

<!--- 70869 -->* Magento no longer displays console errors after CSS merging and minification is enabled. Previously, when CSS merging and minification was enabled, the storefront was not displayed as expected, and the `styles-l.min.css` and `print.min.css` files could not be found. (RC1.8)

<!--- 68969 -->* The contents of the `sales_sequence_meta` table is the same whether you install or upgrade Magento. (RC1.8)









### Catalog

<!--- 70066 -->* We’ve improved the performance of the CatalogPermissions indexer in installations that contain many customer groups.

<!--- 66480 -->* You can now successfully create a product  and assign it to a store without encountering the following error: `Unique constraint violation found`. [GitHub-6671](https://github.com/magento/magento2/issues/6671)

<!--- 62637 -->* You can now successfully set the **Enable Product** attribute to **no**. 

<!--- 70790 -->* You can now remove custom options from simple products. Previously, when you tried to remove a custom option from a product, Magento did not remove the options, and displayed an error message. (RC1.6) 



### Checkout

<!--- 70618 -->* Errors in shipping rates no longer occur when a customer changes the country during guest checkout and DHL is enabled. Previously,  a customer changing country during guest checkout resulted in inaccurate shipping rates. (RC1.6)



<!--- 70646 -->* You can now save the settings you enter when creating a shipping label on an existing shipment.  Previously, clicking the Save button resulted in an error, and the shipping label was not saved. (RC1.5)



### Import/export

<!--- 67240 -->* Magento now displays more verbose information about duplicated information with links to action for troubleshooting the import process.  Previously, Magento displayed duplicated or incomplete information on the product page after import. (RC1.5)

<!--- 65667 -->* Magento now successfully imports customer multiselect attributes. Previously, when you imported a CSV file with either the option's ID numbers or the option's values, Magento returned an error. (RC1.5)




### Magento Business Intelligence

<!--- 69615 -->* Requests for data transfer from Magento to MBI data now complete successfully. 




### Miscellaneous

<!--- 69657 -->* Credit card information now persists as expected after a user enters a promotion code during checkout. Previously, After an user enters credit card information, then discount code and then press "Place Order". The credit card information fields are emptied and user has to enter the credit card information again to proceed with  the order transaction.

<!--- 56062 -->* The Recently Viewed Products block now appears as expected when the full page cache is enabled. [GitHub-3890](https://github.com/magento/magento2/issues/3890)

<!--- 59514 -->* The `tax_region_id` value is no longer hard-coded in the `\Magento\Tax\Setup\InstallData` file. 

<!--- 69964 -->* PHPCS can now correctly parse the syntax of PHP 7.x return types. 

<!--- 67619 -->* The Customer Segment page no longer shows non-matching customers when a customer logs in and you refresh the Customer Segment page. 


<!--- 69750 -->* Magento now successfully completes checkout when a custom address attribute is added. Previously, an error occurred during checkout when the user added a required custom address attribute. 


<!--- 70628 -->* The Forgot Your Password? email now contains a link to reset your password. Previously, this link was missing from the Forgot Your Password? email. (RC1.5)





<!--- 69521 -->* Magento now shows customer attributes in the Admin panel (as expected)  when the **Show on Storefront** option is set to **No**. Previously, when this setting was set to **No**, the attribute value would not appear in the customer account  section of the Admin panel customer account, but did appear in the orders section. (RC1.5)


<!--- 67048 -->* You can now add a `translate` attribute to any String argument in the `di.xml` file for any class. This attribute provides an ability on the level of dependency injection configuration to specify that an argument can be translated. The actual translation of strings is handled by another Magento component. (RC1.6)



<!--- 70642 -->* You can upload a new logo (or change other display features) when editing a transactional email. Previously, Magento crashed after you tried to save changes you may have made to this feature. (RC1.6)



<!--- 70517 -->* You can now successfully check out when the **Deferred Stock Update** option is enabled, and the AMQP connection  is not configured. Previously, checkout failed, and Magento displayed this message:  
	Error Connecting to server (0): Failed to parse address ":" {"exception":"[object](PhpAmqpLib\\Exception\\AMQPRuntimeException(code: 0): Error Connecting to server (0): Failed to parse address \":\" at vendor/php-amqplib/php-amqplib/PhpAmqpLib/Wire/IO/StreamIO.php:106)"} []
(RC1.6)


<!--- 70628 -->* The Forgot Your Password? email now includes an active link to reset your password. (RC1.6)

<!--- 62405 -->* Magento no longer discounts items that belong to an excluded category. Previously, you were unable to exclude products assigned to a specific category due to the cart price rule. (RC1.6)


<!--- 64901 -->* Magento now supports new top level domains for email addresses. [GitHub-4547](https://github.com/magento/magento2/issues/4547) (RC1.6)

<!--- 70518 -->* You can now override publishers configuration through the `env.php` file. (RC1.6)


<!--- 67296 -->* String localizations now works as expected when  phrases include text wrapped with single quotation marks. (RC1.6)


<!--- 70473 -->* Magento now displays company information on the Account Information section of the  Invoice, CreditMemo and Shipment pages. (RC1.8)


<!--- 70683 -->* Magento now displays newly registered customers in the Admin customer list as expected. (RC1.8)

<!--- 69606 -->* We’ve resolved a conflict that occurred after you changed a base URL. Previously, after you changed a `base_url` value (**Stores->Configuration->General->Web-> Base URLs (Secure)**), Magento would update the base URL, then resubscribe, potentially resulting in a failure during the next update secure `base_url` call. 


### Performance

<!--- 69904 -->* We’ve fixed an issue where errors occurred  in foreign keys after Magento added a message to the message queue. Previously, when a user configured a shared catalog, Magento front-end performance was detrimentally affected. (RC1.8)

<!--- 70406 -->* We’ve improved the performance of the CatalogPermission indexer. Previously, Magento performance degraded significantly during the indexing of large numbers of customer groups.(RC1.5)



### REST API

<!--- 70743 -->* You can now use a REST request  to retrieve a shopping cart that contained a product with custom options.  Previously,  you could not use a REST request  to retrieve a shopping cart that contained a product with custom options. (RC1.8)

<!--- 57753 -->* You can now successfully create product attributes using the REST API. Previously, although the product was created, the attribute was not. [GitHub-6213](https://github.com/magento/magento2/issues/6213) (RC1.5)




### Search

<!--- 63249 -->* ElasticSearch now includes data about composite products in its search index. Previously, search results did not include data about composite products. 

<!--- 59477 -->* Attribute weighting now works correctly for the MySQL adapter. [GitHub-9020](https://github.com/magento/magento2/issues/9020) (RC1.5)

<!--- 65245 -->* Magento now sends the `parent_id` of a deleted configurable product variation to ElasticSearch. Previously, Magento didn’t send this information  to the ElasticSearch server  if  the simple product associated with a configurable product were changed. (RC1.5)


### Shipping

<!--- 70844 -->* The DHL provider option is now available. (RC1.8)


### Staging

<!--- 70922 -->* Magento now applies all scheduled product changes to all scopes.  (RC1.8)

<!--- 70656 -->* Magento now displays the correct content on the preview page for a scheduled update.  (RC1.8)


### Tax rules

<!--- 70641 -->* You can now create a tax rule when running Magento in Mozilla Firefox and Internet Explorer. Previously, you could not select a tax rate, and Magento displayed an error.  (RC1.8)

<!--- 59801 -->* We’ve improved the performance of the Tax Rules form in installations containing many tax rates. 



### URL rewrites

<!--- 70663 -->* You can now assign products to a category when  **Match Products by rule** is enabled. (RC1.6)


<!--- 70651 -->* URL rewrites now occur as expected when category or products are saved. Previously, URLs rewrites did not occur for all categories. (RC1.6)


### Visual Merchandiser

<!--- 70896 -->* The Add products by SKU option now works as expected. Previously, if you entered a product SKU, Magento deleted that product from the product list. (RC1.8)




## System requirements
Our technology stack is built on PHP and MySQL. For more information, see [System Requirements]({{ page.baseurl }}install-gde/system-requirements-tech.html).

## Installation

Installation instructions for all versions of this Release Candidate are documented [here]({{ page.baseurl }}release-notes/release-candidate/install.html).


## Credits
Dear community members, thank you for your suggestions and bug reports.