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
Gravity PDF can be run on most shared web hosting, however there are some restrictions in place to prevent problems. The easiest way to check if your web server meets the criteria is to [install](#installation) the plugin. The software has multiple checks in place when activating and will let you know if there are any issues than need addressing. 

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

### Installation [(#installation)](#installation){#installation}
There are multiple ways to install Gravity PDF but the simplest option is to do so via your WordPress admin area.

#### Automatically [(#automatically)](#automatically){#automatically}

1. Login to your WordPress admin area and navigate to the `Plugins -> Add New` page.
1. Use the search bar in the top right hand corner of the plugins page to search for `Gravity PDF`
1. Click the `Install Now` button on the Gravity PDF plugin to confirm the installation. 
1. Once the installation has completed select the `Activate Now` link. 

#### Manually [(#manual)](#manual){#manual}

#### FTP [(#ftp)](#ftp){#ftp}



[^1]: Gravity PDF is not an official Gravity Forms add on - we're an independent company who love how easy the software is. We have no control over their pricing model and we do *not* provide support for their software - you'll want to use [their official support channels](https://www.gravityhelp.com/support/) for that. 
