---
ID: 1444
post_title: Installation
author: GravityBot
post_date: 2015-10-05 02:39:53
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-installation/
published: true
---
<img src="https://gpdfv4.pv/app/uploads/2015/10/welcome-screen.png" alt="Gravity PDF 4.x Welcome Screen" />

Gravity PDF is a <strong>free</strong> WordPress plugin built for the popular premium form builder software, <a href="https://www.e-junkie.com/ecom/gb.php?cl=54585&amp;c=ib&amp;aff=235154">Gravity Forms</a>. It allows you to generate PDF documents that contain user-data captured with Gravity Forms.

The look and feel of the PDF is controlled through templates. The software comes with five <strong>free</strong> designs, but you can also <a href="#">purchase additional templates from our theme shop</a>, <a href="#">build your own using HTML and CSS</a> or have our team <a href="#">custom-build one for you</a> - we can even <a href="#">auto-complete existing PDF documents</a> like government forms.

<hr />

<h3>Plugin Requirements <a href="#requirements" title="" id="requirements">#requirements</a></h3>

<blockquote>
  Gravity PDF is a <strong>third party extension</strong><sup id="fnref-1444-1"><a href="#fn-1444-1" rel="footnote">1</a></sup> for <a href="https://www.e-junkie.com/ecom/gb.php?cl=54585&amp;c=ib&amp;aff=235154">Gravity Forms</a>. The software cannot function without it. You'll need to <a href="https://www.e-junkie.com/ecom/gb.php?cl=54585&amp;c=ib&amp;aff=235154">purchase a license</a> for Gravity Forms before you can use Gravity PDF - any license type will work. <a href="https://gpdfv4.pv/v4-docs/gravity-forms-compatibility/">See more details about Gravity PDF's compatibility with Gravity Forms</a>.
</blockquote>

Gravity PDF can be run on most shared web hosting, however there are some restrictions in place to prevent problems. The easiest way to check if your web server meets the criteria is to <a href="#install">install</a> the plugin. The software has multiple checks in place when activating and will let you know if there are any issues than need addressing.

<strong>Software Requirements</strong>

<ul>
<li><a href="https://www.e-junkie.com/ecom/gb.php?cl=54585&amp;c=ib&amp;aff=235154">Gravity Forms</a> 1.8+ (Gravity Forms 1.9+ recommended). <a href="https://gpdfv4.pv/v4-docs/gravity-forms-compatibility/#gravityforms-licenses">Any license type will work</a>.</li>
<li>WordPress 3.9+ (WordPress 4.2+ recommended)</li>
</ul>

<strong>Server Requirements</strong>

<ul>
<li>PHP 5.3+ (PHP 5.6+ recommended)</li>
<li><a href="http://www.php.net/manual/en/mbstring.installation.php">MB String</a> with Regex enabled (<code>--enable-mbregex</code>)</li>
<li><a href="http://www.php.net/manual/en/image.installation.php">GD Library</a></li>
<li><a href="http://php.net/manual/en/intro.dom.php">DOM</a></li>
<li>64MB+ WP Memory (<strong>128MB+ recommended</strong>)</li>
</ul>

<h3>Installation <a href="#install" title="" id="install">#install</a></h3>

There are multiple ways to install Gravity PDF but the simplest option is to do so via your WordPress admin area.

<strong>Jump to section</strong>

<ol>
<li><a href="#automatic">Automatic Installation</a> (recommended)</li>
<li><a href="#manual">Manual Installation</a></li>
<li><a href="#ftp">FTP Installation</a></li>
</ol>

<hr />

<h4>Automatic Installation <a href="#automatic" title="" id="automatic">#automatic</a></h4>

Search for the plugin directly from your WordPress admin area and install it with a single click.

<ol>
<li>Login to your WordPress admin area and navigate to the <code>Plugins -&gt; Add New</code> page.</li>
<li>Use the search bar in the top right hand corner of the plugins page to search for <code>Gravity PDF</code>.
<img src="https://gpdfv4.pv/app/uploads/2015/10/automatic-install.png" alt="Plugin Installation Screen" /></li>
<li>Click the <code>Install Now</code> button on the Gravity PDF plugin to confirm the installation. </li>
<li>Once the installation has completed select the <code>Activate Now</code> link. 
<img src="https://gpdfv4.pv/app/uploads/2015/10/activate-gravity-pdf.png" alt="Activate Plugin" /></li>
</ol>

<hr />

<h4>Manually Installation <a href="#manual" title="" id="manual">#manual</a></h4>

Download the plugin zip file from WordPress.org and upload through your WordPress admin area<sup id="fnref-1444-2"><a href="#fn-1444-2" rel="footnote">2</a></sup>.

<ol>
<li>Access the plugin's <a href="https://wordpress.org/plugins/gravity-forms-pdf-extended/">WordPress repository</a> and select the <code>Download Version 4.x.x</code> button.
<img src="https://gpdfv4.pv/app/uploads/2015/10/download-plugin.png" alt="Download the zip file" /></li>
<li>In your WordPress admin area, navigate to the <code>Plugins -&gt; Add New</code> page then select the <code>Upload Plugin</code> button (located to the right of the <code>Add Plugins</code> title)</li>
<li>Click the <code>Browse</code> button and select the zip file downloaded in step one. 
<img src="https://gpdfv4.pv/app/uploads/2015/10/manual-plugin-installation.png" alt="Manual Plugin Installation" /></li>
<li>Click the <code>Install Now</code> button and wait. Depending on your internet speed, it could take some time to upload.</li>
<li>Once installed, select the <code>Activate Now</code> link.</li>
</ol>

<hr />

<h4>FTP Installation <a href="#ftp" title="" id="ftp">#ftp</a></h4>

Upload the Gravity PDF plugin files to the WordPress plugins directory using your favourite FTP client.

<ol>
<li>Navigate to the plugin's <a href="https://wordpress.org/plugins/gravity-forms-pdf-extended/">WordPress repository</a> and select the <code>Download Version 4.x.x</code> button.</li>
<li>Once downloaded, unzip the plugin folder. A folder called <code>gravity-forms-pdf-extended</code> will be extracted and this is what you should upload to your FTP server.</li>
<li>Open your favourite FTP client (we recommend <a href="https://filezilla-project.org/">Filezilla</a>) and enter your hostname, username and password. If you are unsure where to get these details you should contact your web hosting provider for assistance.</li>
<li>Once logged in, navigate to your WordPress plugin directory (usually <code>/wp-content/plugins/</code>) and upload the <code>gravity-forms-pdf-extended</code> folder. If a directory called <code>gravity-forms-pdf-extended</code> already exists, delete it before uploading.
<img src="https://gpdfv4.pv/app/uploads/2015/10/ftp-upload.png" alt="Upload plugin via FTP" /></li>
<li>Finally activate the plugin via your WordPress admin plugins page <code>Plugins -&gt; Installed Plugins</code></li>
</ol>

<div class="footnotes">
<hr />
<ol>

<li id="fn-1444-1">
Gravity PDF is not an official Gravity Forms add on - we're an independent company who love how powerful Gravity Forms is. We have no control over their pricing model and we do <em>not</em> provide support for their software - you'll want to use <a href="https://www.gravityhelp.com/support/">their official support channels</a> for that.&#160;<a href="#fnref-1444-1" rev="footnote">&#8617;</a>
</li>

<li id="fn-1444-2">
The plugin zip file is just over 18MB. Some web hosting providers are not configured to accept file uploads of that size. If this is the case you should use the <a href="#automatic">automatic</a> or <a href="#ftp">FTP</a> method of installation.&#160;<a href="#fnref-1444-2" rev="footnote">&#8617;</a>
</li>

</ol>
</div>