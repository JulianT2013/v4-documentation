---
ID: 1444
post_title: Installation
author: GravityBot
post_date: 2015-10-05 02:39:53
post_excerpt: ""
layout: v4_docs
permalink: https://gpdfv4.pv/v4-docs/installation/
published: true
---
![Gravity PDF 4.x Welcome Screen](https://gpdfv4.pv/app/uploads/2015/10/welcome-screen.png)

Gravity PDF can be run on most shared web hosting, however there are some restrictions in place to prevent problems. The easiest way to check if your web server meets the criteria is to [install](#install) the plugin. The software has multiple checks in place when activating and will let you know if there are any issues than need addressing. 

### Plugin Requirements [(#requirements)](#requirements){#requirements}
Gravity PDF is a **third party extension**[^1] for the popular premium forms plugin, [Gravity Forms](https://www.e-junkie.com/ecom/gb.php?cl=54585&c=ib&aff=235154). The software cannot function without it. You'll need to [purchase a license](https://www.e-junkie.com/ecom/gb.php?cl=54585&c=ib&aff=235154) for Gravity Forms before you can use Gravity PDF.

**Software Requirements**

* [Gravity Forms](https://www.e-junkie.com/ecom/gb.php?cl=54585&c=ib&aff=235154) 1.8+ (Gravity Forms 1.9 recommended). Any license type will work.
* WordPress 3.9+ (WordPress 4.2 recommended)

**Server Requirements**

* PHP 5.3+ (PHP 5.6 recommended)
* [MB String](http://www.php.net/manual/en/mbstring.installation.php) with Regex enabled (`--enable-mbregex`)
* [GD Library](http://www.php.net/manual/en/image.installation.php)
* 64MB+ WP Memory (**128MB+ recommended**)

### Installation [(#install)](#install){#install}
There are multiple ways to install Gravity PDF but the simplest option is to do so via your WordPress admin area.

**Jump to section**

1. [Automatic Installation](#automatic) (recommended)
1. [Manual Installation](#manual)
1. [FTP Installation](#ftp)

#### Automatically [(#automatic)](#automatic){#automatic}

1. Login to your WordPress admin area and navigate to the `Plugins -> Add New` page.
1. Use the search bar in the top right hand corner of the plugins page to search for `Gravity PDF`.
   ![Plugin Installation Screen](https://gpdfv4.pv/app/uploads/2015/10/automatic-install.png)
1. Click the `Install Now` button on the Gravity PDF plugin to confirm the installation. 
1. Once the installation has completed select the `Activate Now` link. 
   ![Activate Plugin](https://gpdfv4.pv/app/uploads/2015/10/activate-gravity-pdf.png)

#### Manually [(#manual)](#manual){#manual}
1. Access the plugin's [WordPress repository](https://wordpress.org/plugins/gravity-forms-pdf-extended/) and select the `Download Version 4.x.x` button.
   ![Download the latest version of the plugin](https://gpdfv4.pv/app/uploads/2015/10/download-plugin.png)
1. In your WordPress admin area, navigate to the `Plugins -> Add New` page then select the `Upload Plugin` button (located to the right of the `Add Plugin` title)
1. Click the `Browse` button and select the zip file downloaded in step one.
   ![Manual Plugin Installation](https://gpdfv4.pv/app/uploads/2015/10/https://gpdfv4.pv/app/uploads/2015/10/manual-plugin-installation.png)
1. Once complete, select the `Activate Now` link.

The plugin zip file is just over 18MB. Some web hosting providers are not configured to accept file uploads of that size. If this is the case you should use the [automatic](#automatic) or [FTP](#ftp) method of installation.

#### FTP [(#ftp)](#ftp){#ftp}

1. Navigate to the plugin's [WordPress repository](https://wordpress.org/plugins/gravity-forms-pdf-extended/) and select the `Download Version 4.x.x` button.
1. Once downloaded, unzip the plugin folder. A folder called `gravity-forms-pdf-extended` will be extracted and this is what you should upload to your FTP server.
1. Open your favourite FTP client (we recommend [Filezilla](https://filezilla-project.org/)) and enter your hostname, username and password. If you are unsure where to get these details you should contact your web hosting provider for assistance.
1. Once logged in, navigate to your WordPress plugin directory (usually `/wp-content/plugins/`) and upload the `gravity-forms-pdf-extended` folder. 
1. Finally activate the plugin via your WordPress admin plugins page `Plugins -> Installed Plugins`


[^1]: Gravity PDF is not an official Gravity Forms add on - we're an independent company who love how powerful Gravity Forms is. We have no control over their pricing model and we do *not* provide support for their software - you'll want to use [their official support channels](https://www.gravityhelp.com/support/) for that. 
