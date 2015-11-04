---
ID: 1469
post_title: Activation Errors
author: GravityBot
post_date: 2015-10-22 02:41:39
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-activation-errors/
published: true
---
When Gravity PDF is activated it will run a number of checks to ensure your web server meets all the <a href="#">software requirements</a>. It also verifies the minimum version requirements for WordPress and Gravity Form. If it detects a problem a notice will be displayed in your admin area.

<strong>Jump to Section</strong>

<ul>
<li><a href="#wordpress-version">WordPress Version 4.X is required</a></li>
<li><a href="#gravityforms-version">Gravity Forms Version 1.x is required</a></li>
<li><a href="#php-version">You are running an outdated version of PHP</a></li>
<li><a href="#php-mbstring">The PHP Extension MB String could not be detected</a> </li>
<li><a href="#php-mbstring-regex">The PHP Extension MB String does not have MB Regex enabled</a></li>
<li><a href="#php-gd">The PHP Extension GD Image Library could not be detected</a></li>
<li><a href="#php-dom">The PHP DOM Extension was not found</a></li>
<li><a href="#php-xml">The PHP Extension libxml could not be detected</a></li>
<li><a href="#wp-memory">You need 128MB of WP Memory (RAM) but we only found X available</a></li>
</ul>

<hr />

<h4>WordPress Version 4.X is required <a href="#wordpress-version" title="" id="wordpress-version">#wordpress-version</a></h4>

This error means your WordPress software doesn't meet the minimum software requirements – currently WordPress 3.9 and above are supported. To resolve the issue use WordPress' One-Click Update feature to get the latest version. Navigate to <code>Dashboard &gt; Updates</code> in your admin area to update WordPress.

<hr />

<h4>Gravity Forms Version 1.x is required <a href="#gravityforms-version" title="" id="gravityforms-version">#gravityforms-version</a></h4>

This error means your version of Gravity Forms doesn't meet the minimum software requirements – currently Gravity Forms 1.8 and above are supported. To resolve the issue use Gravity Forms' automatic updater to get the latest version. Navigate to <code>Forms -&gt; Updates</code> in your admin area to update Gravity Forms. <strong>One-click updates require an activate Gravity Forms license key</strong>.

<hr />

<h4>You are running an outdated version of PHP <a href="#php-version" title="" id="php-version">#php-version</a></h4>

This error means the version of PHP running on your website's web server isn't compatible – currently version 5.3 and above are supported. To fix this issue you'll need to contact your web hosting provider and ask them to switch you to the latest version of PHP – currently version 5.6.

<hr />

<h4>The PHP Extension MB String could not be detected <a href="#php-mbstring" title="" id="php-mbstring">#php-mbstring</a></h4>

This error means the version of PHP you are running doesn't have support for MB String. This extension is used to correctly display non-English characters in PDF documents. To fix this issue you'll need to contact your web hosting and tell them you need MB String enabled.

<hr />

<h4>The PHP Extension MB String does not have MB Regex enabled <a href="#php-mbstring-regex" title="" id="php-mbstring-regex">#php-mbstring-regex</a></h4>

This error means the version of PHP you are running does have the <a href="#php-mbstring">MB String</a> module installed, but doesn't have support for the regular expression functions which usually come bundled with this extension. To fix this issue you'll need to contact your web hosting and tell them you need MB String's Regex functions enabled.

<hr />

<h4>The PHP Extension GD Image Library could not be detected <a href="#php-gd" title="" id="php-gd">#php-gd</a></h4>

This error means the version of PHP you are running doesn't have the GD Image Library installed. This is used to correctly display images in the PDF documents. To fix this issue you'll need to contact your web hosting and tell them you need the GD Image Library installed with jpeg and png support.

<hr />

<h4>The PHP DOM Extension was not found <a href="#php-dom" title="" id="php-dom">#php-dom</a></h4>

This error means the version of PHP you are running doesn't have the DOM extension installed. This is used to correct certain display issues when generating PDFs. To fix this issue you'll need to contact your web hosting and tell them you need the DOM extension installed.

<hr />

<h4>The PHP Extension libxml could not be detected <a href="#php-xml" title="" id="php-xml">#php-xml</a></h4>

This error means the version of PHP you are running doesn't have the LibXML extension installed. This is needed by the <a href="#php-dom">DOM</a> extension. To fix this issue you'll need to contact your web hosting and tell them you need the LibXML extension installed.

<hr />

<h4>You need 128MB of WP Memory (RAM) but we only found X available <a href="#wp-memory" title="" id="wp-memory">#wp-memory</a></h4>

This error means the WordPress memory limit isn't high enough. Generating PDF documents is hard work and uses a lot of resources, which is why it needs more memory. <a href="https://gpdfv4.pv/v4-docs/increasing-memory-limit/">Read our guide on how you can increase your memory limit</a> to fix the problem.