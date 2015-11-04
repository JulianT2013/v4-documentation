---
ID: 1458
post_title: Global Settings
author: GravityBot
post_date: 2015-10-11 03:47:48
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-global-settings/
published: true
---
<img src="https://gpdfv4.pv/app/uploads/2015/10/general-settings.png" alt="Gravity PDF Global Settings Page" />

Gravity PDF is fully integrated into Gravity Forms. The PDF settings are located in a separate section in Gravity Forms own settings area. You can find them by navigating to <code>Forms -&gt; Settings -&gt; PDF</code> in your WordPress admin area.

The PDF settings are split into three separate tabs:

<ul>
<li><a href="#general">General</a>: The basics (including PDF defaults) and security</li>
<li><a href="#tools">Tools</a>: Power user actions </li>
<li><a href="#help">Help</a>: Search our documentation for assistance</li>
</ul>

<hr />

<h3>General Tab <a href="#general" title="" id="general">#general</a></h3>

From here you'll be able to control the PDF defaults like paper size, font and template. You also have advanced options giving you granular control over the security protocols.

This tab is only available to users with the <code>gravityforms_view_settings</code> capability. By default this is administrators and network super admins (if running a multisite).

<dl>
<dt>Default Paper Size <a href="#paper-size" title="" id="paper-size">#paper-size</a></dt>
<dd>
Use this option to set the paper size for all <a href="#">individual PDF settings</a>. The default selection is A4 (210 x 297mm), but other common paper sizes – such as US Letter and Legal – are easily accessible. Also preloaded are the ISO-standard <em>A</em>, <em>B</em> and <em>C</em> paper sizes, as well as <em>RA</em> and <em>SRA</em>.

If none of the preloaded options suit you can also select <em>Custom Paper Size</em> (see <a href="#custom-paper-size">#custom-paper-size</a> below) and control the width and height in millimetres or inches.
</dd>

<dt>Custom Paper Size <a href="#custom-paper-size" title="" id="custom-paper-size">#custom-paper-size</a></dt>
<dd>This field is hidden until you select the <em>Custom Template Option</em> from the <em>Default Paper Size</em> field (see <a href="#paper-size">#paper-size</a> above). It allows you to control the exact paper size of your document – in millimetres or inches. When displayed, this field is required and only positive numbers are permitted in the width and height inputs.</dd>

<dt>Default Template <a href="#default-template" title="" id="default-template">#default-template</a></dt>
<dd>Use this option to set the default template for all <a href="#">individual PDF settings</a> – templates control the PDF design and layout. Gravity PDF comes with five <strong>completely-free</strong> templates for you to choose from. Upon changing your selection (using the drop down) an image will load showing you what the chosen template looks like.</dd>

<dd>The default template is <em>Zadani</em> – a minimalist business-style template that will generate a well-spaced document great for printing. Additional templates can be purchased from our <a href="#">theme shop</a>.</dd>

<dd>Developers with HTML, CSS and a little PHP knowledge can <a href="#">create their own designs and layouts</a>. Alternatively, the Gravity PDF team offers <a href="#">design and integration services</a> for those looking for a custom solution – we can even <a href="#">integrate an exiting PDF document</a>.</dd>

<dt>Default Font Type <a href="#font-type" title="" id="font-size">#font-type</a></dt>
<dd>Use this option to set the default font for all <a href="#">individual PDF settings</a>. Gravity PDF ships with fonts for the majority of languages worldwide and uses the unicode typeface <em>DejaVu Sans Condensed</em> by default. For languages that aren't supported out of the box, you can use our <a href="#fonts">Font Installer</a> to upload TTF or OTF font files for use in PDFs.</dd>

<dt>Default Font Size <a href="#font-size" title="" id="font-size">#font-size</a></dt>
<dd>Use this option to set the default font size for all <a href="#">individual PDF settings</a>. The default is set to 12pt. Increase or decrease to suit your font type.</dd>

<dt>Default Font Colour <a href="#font-colour" title="" id="font-colour">#font-colour</a></dt>
<dd>Use this option to set the default font colour for all <a href="#">individual PDF settings</a>. The default is set to black (hex colour code #000000).</dd>

<dt>Reverse Text (RTL) <a href="#rtl" title="" id="rtl">#rtl</a></dt>
<dd>
Use this option to default the text direction for all <a href="#">individual PDF settings</a>. Many languages worldwide are written from right to left – Arabic and Hebrew script are examples of this.

The default is set to <em>No</em>, disabling RTL support.
</dd>

<dt>Entry View <a href="#view" title="" id="view">#view</a></dt>
<dd>Once a PDF has been created for a particular form a PDF link is added to the form's entry list page. When the link is selected this option determines if the PDF will be viewed in your browser or prompted for download. By default this option is set to <code>View</code>.</dd>

<dt>Show What's New <a href="#whats-new" title="" id="whats-new">#whats-new</a></dt>
<dd>
When the plugin is upgraded to a new major release (4.x) we automatically direct you to our <em>What's New</em> page to give you an overview of, well, what's new!

We've made this feature as unobtrusive as possible, which is why bug fixes and security released (4.0.x) are excluded from triggering this behaviour. Also, only users that can activate plugins will be redirected (usually site administrators and, if running a multisite, network super admins). Deactivating then reactivating the plugin won't trigger the redirect either.

By default this option is set to <code>Enable</code>.
</dd>
</dl>

<h4>Advanced Options <a href="#general-advanced-options" title="" id="general-advanced-options">#general-advanced-options</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/security-settings.png" alt="Gravity PDF Advanced Options on the General Tab" title="" class="aligncenter" />

The advanced options focuses on PDF security and can be shown by clicking the <code>Show Advanced Options...</code> link (just above the <em>Save Changes</em> button). The security settings are configured with sane defaults and in most cases you won't need to modify this behaviour. Our <a href="#">security documentation page</a> focuses or the finer points of the plugin's security protocols and is worth a read before changing these options.

<dl>
<dt>User Restriction <a href="#user-restriction" title="" id="user-restriction">#user-restriction</a></dt>
<dd>
Logged in users without the <code>gravity_forms_view_entries</code> capability are prevented from accessing any PDF if they aren't the original owner – the owner is who filled in the form entry originally. If you leave the setting untouched only site administrators and network super admins (if running a multisite) can view the generated PDFs.

To change this behaviour you can assign capabilities that other roles have access to. For instance, if you wanted the <a href="https://codex.wordpress.org/Roles_and_Capabilities#Editor"><em>Editor</em> role</a> to have access to PDFs you could add the <code>edit_pages</code> capability.

Alternatively, instead of adding additional capabilities to this field you could use a role editing plugin like <a href="https://wordpress.org/plugins/user-role-editor/">User Role Editor</a> to give an existing role the <code>gravity_forms_view_entries</code> capability. Choose the best solution for your use-case.
</dd>

<dd>
This option has no effect on PDFs sent as attachments in Gravity Form notifications but does effect the <code>[gravitypdf]</code> shortcode.
</dd>

<dd>More information about WordPress roles and capabilities <a href="https://codex.wordpress.org/Roles_and_Capabilities">can be found in the WordPress codex</a>.</dd>

<dt>Restrict Owner <a href="#restrict-owner" title="" id="restrict-owner">#restrict-owner</a></dt>
<dd>This option allows you to prevent the form entry owner – the user who filled out the Gravity Form – from viewing the generated PDF. This included logged out and logged in users – with the exception of a logged in user who has any of the capabilities listed in the <a href="#user-restriction">#user-restriction</a> field.</dd>

<dd>This option has no effect on PDFs sent as attachments in Gravity Form notifications but does effect the <code>[gravitypdf]</code> shortcode.</dd>

<dd>The default option is <code>No</code>.</dd>

<dt>Logged Out Timeout <a href="#logged-out-timeout" title="" id="logged-out-timeout">#logged-out-timeout</a></dt>
<dd>When a logged out user attempts to view a PDF the plugin will try and match their current IP address against the one saved with the Gravity Forms entry. If they match they get access. However, this method isn't a secure long-term option <a href="http://whatismyipaddress.com/keeps-changing">because IP addresses can change</a>. To prevent unauthorised access we implemented a timeout feature. After X amount of time the user no longer has access to the generated PDF.</dd>

<dd>This option has no effect on PDFs sent as attachments in Gravity Form notifications but does effect the <code>[gravitypdf]</code> shortcode.</dd>

<dd>By default this timeout is set to 30 minutes. <strong>While it is not recommended</strong> you can disable this feature by setting the timeout to zero (0).</dd>
</dl>

<hr />

<h3>Tools Tab <a href="#tools" title="" id="tools">#tools</a></h3>

<img src="https://gpdfv4.pv/app/uploads/2015/10/tools-tab.png" alt="Gravity PDF Tools Settings Page" />

The tools tab contains useful functions for power users. You can install additional fonts for use in your PDF documents, prepare your system for custom PDF templates and uninstall the plugin.

This tab is only available to users with the <code>gravityforms_edit_settings</code> capability. By default this is administrators and network super admins (if running a multisite).

<dl>
<dt>Setup Custom Templates <a href="#custom-templates" title="" id="custom-templates">#custom-templates</a></dt>
<dd>
Gravity PDF uses a templating system similar to WordPress' child themes. The core templates that ship with the plugin are located in the <code>/initialisation/templates/</code> directory (it acts like a parent theme), however you cannot modify these files without losing your changes when the plugin is updated. To circumvent this issue templates can be placed in the plugin's working directory <code>/wp-content/uploads/PDF_EXTENDED_TEMPLATES/</code> (the child theme in our analogy). From here you can edit the templates as you see fit and you won't loose your modifications during updates.

The <em>Setup Custom Templates</em> option copies all the core templates to the <code>PDF_EXTENDED_TEMPLATES</code> directory. If you have previously run this setup the core files in your <code>PDF_EXTENDED_TEMPLATES</code> directory will be overridden.

Before running this function it's recommended you <a href="#">review our developer's guide to templating</a>.
</dd>

<dt>Fonts <a href="#fonts" title="" id="fonts">#fonts</a></dt>
<dd>
The font manager allows you to install any TTF or OTF font and use it in your PDFs. There are two required fields when adding a new font:

<ol>
<li>Unique font name (only alphanumeric characters and spaces must be used)</li>
<li>The URL to the font file (fonts must be uploaded via the Media Library and in TTF or OTF format)</li>
</ol>

If the particular font provides different files for bold, italic and bold italics typefaces you can optionally include them. A faux bold, italic or bold italic style will be rendered in the PDF if they are not set.

Once a font is installed you can select it in the PDF settings. If creating a PDF template you also have the option to set the font family directly using CSS (a helpful snippet is provided).

Review our <a href="#">Font Manager documentation</a> for more in-depth details on managing PDF fonts.
</dd>

<dt>Uninstall <a href="#uninstall" title="" id="uninstall">#uninstall</a></dt>
<dd>This option will completely remove the plugin from your website and clean up the database and file system – it will be as if the software was never installed. <strong>Any custom templates you have will also be deleted</strong>. During the uninstallation the plugin will automatically deactivate and redirect you to the plugins page.</dd>

<dd>When the uninstall button is clicked a warning box will pop up asking you to confirm before continuing.</dd>

<dd>A user must have the <code>gravityforms_uninstall</code> capability to complete this action. By default this is only site administrators. If running a multisite only a network super admin can do the uninstallation.</dd>
</dl>

<hr />

<h3>Help Tab <a href="#help" title="" id="help">#help</a></h3>

<img src="https://gpdfv4.pv/app/uploads/2015/10/help-tab.png" alt="Gravity PDF Help Settings Page" />

Details about the help tab to be refined...