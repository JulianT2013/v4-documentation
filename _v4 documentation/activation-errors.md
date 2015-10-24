---
ID: 1469
post_title: Activation Errors
author: Jake Jackson
post_date: 2015-10-22 02:41:39
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/activation-errors/
published: true
---
When Gravity PDF is activated it will run a number of checks to ensure your web server meets all the [software requirements](#). It also verifies the minimum version requirements for WordPress and Gravity Form. If it detects a problem a notice will be displayed in your admin area. 

**Jump to Section**

* [WordPress Version 4.X is required](#wordpress-version)
* [Gravity Forms Version 1.x is required](#gravityforms-version)
* [You are running an outdated version of PHP](#php-version)
* [The PHP Extension MB String could not be detected](#php-mbstring) 
* [The PHP Extension MB String does not have MB Regex enabled](#php-mbstring-regex)
* [The PHP Extension GD Image Library could not be detected](#php-gd)
* [The PHP DOM Extension was not found](#php-dom)
* [The PHP Extension libxml could not be detected](#php-xml)
* [You need 128MB of WP Memory (RAM) but we only found X available](#wp-memory)


---

#### WordPress Version 4.X is required [#wordpress-version](#wordpress-version){#wordpress-version}

This error means your WordPress software doesn't meet the minimum software requirements – currently WordPress 3.9 and above are supported. To resolve the issue use WordPress' One-Click Update feature to get the latest version. Navigate to `Dashboard > Updates` in your admin area to update WordPress.

---

#### Gravity Forms Version 1.x is required [#gravityforms-version](#gravityforms-version){#gravityforms-version}

This error means your version of Gravity Forms doesn't meet the minimum software requirements – currently Gravity Forms 1.8 and above are supported. To resolve the issue use Gravity Forms' automatic updater to get the latest version. Navigate to `Forms -> Updates` in your admin area to update Gravity Forms. **One-click updates require an activate Gravity Forms license key**.

---

#### You are running an outdated version of PHP [#php-version](#php-version){#php-version}

This error means the version of PHP running on your website's web server isn't compatible – currently version 5.3 and above are supported. To fix this issue you'll need to contact your web hosting provider and ask them to switch you to the latest version of PHP – currently version 5.6.

--- 

#### The PHP Extension MB String could not be detected [#php-mbstring](#php-mbstring){#php-mbstring}

This error means the version of PHP you are running doesn't have support for MB String. This extension is used to correctly display non-English characters in PDF documents. To fix this issue you'll need to contact your web hosting and tell them you need MB String enabled.

---

#### The PHP Extension MB String does not have MB Regex enabled [#php-mbstring-regex](#php-mbstring-regex){#php-mbstring-regex}

This error means the version of PHP you are running does have the [MB String](#php-mbstring) module installed, but doesn't have support for the regular expression functions which usually come bundled with this extension. To fix this issue you'll need to contact your web hosting and tell them you need MB String's Regex functions enabled.

--- 

#### The PHP Extension GD Image Library could not be detected [#php-gd](#php-gd){#php-gd}

This error means the version of PHP you are running doesn't have the GD Image Library installed. This is used to correctly display images in the PDF documents. To fix this issue you'll need to contact your web hosting and tell them you need the GD Image Library installed with jpeg and png support.

--- 

#### The PHP DOM Extension was not found [#php-dom](#php-dom){#php-dom}

This error means the version of PHP you are running doesn't have the DOM extension installed. This is used to correct certain display issues when generating PDFs. To fix this issue you'll need to contact your web hosting and tell them you need the DOM extension installed.

---

#### The PHP Extension libxml could not be detected [#php-xml](#php-xml){#php-xml}

This error means the version of PHP you are running doesn't have the LibXML extension installed. This is needed by the [DOM](#php-dom) extension. To fix this issue you'll need to contact your web hosting and tell them you need the LibXML extension installed.

--- 

#### You need 128MB of WP Memory (RAM) but we only found X available [#wp-memory](#wp-memory){#wp-memory}

This error means the WordPress memory limit isn't high enough. Generating PDF documents is hard work and uses a lot of resources, which is why it needs more memory. [Read our guide on how you can increase your memory limit](https://gpdfv4.pv/v4-docs/increasing-memory-limit/) to fix the problem.