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
![Gravity PDF Global Settings Page](https://gpdfv4.pv/app/uploads/2015/10/general-settings.png) 

Gravity PDF is fully integrated into Gravity Forms. The PDF settings are located in a separate section in Gravity Forms own settings area. You can find them by navigating to `Forms -> Settings -> PDF` in your WordPress admin area. 

The PDF settings are split into three separate tabs:

* [General](#general): The basics (including PDF defaults) and security
* [Tools](#tools): Power user actions
* [Help](#help): Search our documentation for assistance

---

### General Tab [#general](#general){#general}

From here you'll be able to control the PDF defaults like paper size, font and template. You also have advanced options giving you granular control over the security protocols. 

This tab is only available to users with the `gravityforms_view_settings` capability. By default this is administrators and network super admins (if running a multisite).

Default Paper Size [#paper-size](#paper-size){#paper-size}
:    Use this option to set the paper size for all [individual PDF settings](https://gpdfv4.pv/v4-docs/user-setup-pdf/). The default selection is A4 (210 x 297mm), but other common paper sizes – such as US Letter and Legal – are easily accessible. Also preloaded are the ISO-standard *A*, *B* and *C* paper sizes, as well as *RA* and *SRA*. 
:    If none of the preloaded options suit you can also select *Custom Paper Size* (see [#custom-paper-size](#custom-paper-size) below) and control the width and height in millimetres or inches.

Custom Paper Size [#custom-paper-size](#custom-paper-size){#custom-paper-size}
:    This field is hidden until you select the *Custom Template Option* from the *Default Paper Size* field (see [#paper-size](#paper-size) above). It allows you to control the exact paper size of your document – in millimetres or inches. When displayed, this field is required and only positive numbers are permitted in the width and height inputs.

Default Template [#default-template](#default-template){#default-template}
:    Use this option to set the default template for all [individual PDF settings](https://gpdfv4.pv/v4-docs/user-setup-pdf/) – templates control the PDF design and layout. Gravity PDF comes with five **completely-free** templates for you to choose from. Upon changing your selection (using the drop down) an image will load showing you what the chosen template looks like.
:    The default template is *Zadani* – a minimalist business-style template that will generate a well-spaced document great for printing. Additional templates can be purchased from our [theme shop](#).
:    Developers with HTML, CSS and a little PHP knowledge can [create their own designs and layouts](#). Alternatively, the Gravity PDF team offers [design and integration services](#) for those looking for a custom solution – we can even [integrate an exiting PDF document](#).

Default Font Type [#font-type](#font-type){#font-type}
:    Use this option to set the default font for all [individual PDF settings](https://gpdfv4.pv/v4-docs/user-setup-pdf/). Gravity PDF ships with fonts for the majority of languages worldwide and uses the unicode typeface *DejaVu Sans Condensed* by default. For languages that aren't supported out of the box, you can use our [Font Installer](#fonts) to upload TTF or OTF font files for use in PDFs.

Default Font Size [#font-size](#font-size){#font-size}
:    Use this option to set the default font size for all [individual PDF settings](https://gpdfv4.pv/v4-docs/user-setup-pdf/). The default is set to 12pt. Increase or decrease to suit your font type.

Default Font Colour [#font-colour](#font-colour){#font-colour}
:    Use this option to set the default font colour for all [individual PDF settings](https://gpdfv4.pv/v4-docs/user-setup-pdf/). The default is set to black (hex colour code #000000).

Reverse Text (RTL) [#rtl](#rtl){#rtl}
:    Use this option to default the text direction for all [individual PDF settings](https://gpdfv4.pv/v4-docs/user-setup-pdf/). Many languages worldwide are written from right to left – Arabic and Hebrew script are examples of this. The default is set to *No*, disabling RTL support.

Entry View [#view](#view){#view}
:    Once a PDF has been created for a particular form a PDF link is added to the form's entry list page. When the link is selected this option determines if the PDF will be viewed in your browser or prompted for download. By default this option is set to `View`.

Show What's New [#whats-new](#whats-new){#whats-new}
:    When the plugin is upgraded to a new major release (4.x) we automatically direct you to our *What's New* page to give you an overview of, well, what's new! 
:    We've made this feature as unobtrusive as possible, which is why bug fixes and security released (4.0.x) are excluded from triggering this behaviour. Also, only users that can activate plugins will be redirected (usually site administrators and, if running a multisite, network super admins). Deactivating then reactivating the plugin won't trigger the redirect either. 
:    By default this option is set to `Enable`.

#### Advanced Options [#general-advanced-options](#general-advanced-options){#general-advanced-options}

![Gravity PDF Advanced Options on the General Tab](https://gpdfv4.pv/app/uploads/2015/10/security-settings.png){.aligncenter}

The advanced options focuses on PDF security and can be shown by clicking the `Show Advanced Options...` link (just above the *Save Changes* button). The security settings are configured with sane defaults and in most cases you won't need to modify this behaviour. Our [security documentation page](https://gpdfv4.pv/v4-docs/user-pdf-security/) focuses or the finer points of the plugin's security protocols and is worth a read before changing these options.

User Restriction [#user-restriction](#user-restriction){#user-restriction}
:    Logged in users without the `gravity_forms_view_entries` capability are prevented from accessing any PDF if they aren't the original owner – the owner is who filled in the form entry originally. If you leave the setting untouched only site administrators and network super admins (if running a multisite) can view the generated PDFs. 

    To change this behaviour you can assign capabilities that other roles have access to. For instance, if you wanted the [*Editor* role](https://codex.wordpress.org/Roles_and_Capabilities#Editor) to have access to PDFs you could add the `edit_pages` capability. 

    Alternatively, instead of adding additional capabilities to this field you could use a role editing plugin like [User Role Editor](https://wordpress.org/plugins/user-role-editor/) to give an existing role the `gravity_forms_view_entries` capability. Choose the best solution for your use-case.
:    This option has no effect on PDFs sent as attachments in Gravity Form notifications but does effect the `[gravitypdf]` shortcode.
:    More information about WordPress roles and capabilities [can be found in the WordPress codex](https://codex.wordpress.org/Roles_and_Capabilities).

Restrict Owner [#restrict-owner](#restrict-owner){#restrict-owner}
:    This option allows you to prevent the form entry owner – the user who filled out the Gravity Form – from viewing the generated PDF. This included logged out and logged in users – with the exception of a logged in user who has any of the capabilities listed in the [#user-restriction](#user-restriction) field.
:    This option has no effect on PDFs sent as attachments in Gravity Form notifications but does effect the `[gravitypdf]` shortcode.
:    The default option is `No`.

Logged Out Timeout [#logged-out-timeout](#logged-out-timeout){#logged-out-timeout}
:    When a logged out user attempts to view a PDF the plugin will try and match their current IP address against the one saved with the Gravity Forms entry. If they match they get access. However, this method isn't a secure long-term option [because IP addresses can change](http://whatismyipaddress.com/keeps-changing). To prevent unauthorised access we implemented a timeout feature. After X amount of time the user no longer has access to the generated PDF.
:    This option has no effect on PDFs sent as attachments in Gravity Form notifications but does effect the `[gravitypdf]` shortcode.
:    By default this timeout is set to 30 minutes. **While it is not recommended** you can disable this feature by setting the timeout to zero (0).

---

### Tools Tab [#tools](#tools){#tools}

![Gravity PDF Tools Settings Page](https://gpdfv4.pv/app/uploads/2015/10/tools-tab.png) 

The tools tab contains useful functions for power users. You can install additional fonts for use in your PDF documents, prepare your system for custom PDF templates and uninstall the plugin. 

This tab is only available to users with the `gravityforms_edit_settings` capability. By default this is administrators and network super admins (if running a multisite).

Setup Custom Templates [#custom-templates](#custom-templates){#custom-templates}
:    Gravity PDF uses a templating system similar to WordPress' child themes. The core templates that ship with the plugin are located in the `/initialisation/templates/` directory (it acts like a parent theme), however you cannot modify these files without losing your changes when the plugin is updated. To circumvent this issue templates can be placed in the plugin's working directory `/wp-content/uploads/PDF_EXTENDED_TEMPLATES/` (the child theme in our analogy). From here you can edit the templates as you see fit and you won't loose your modifications during updates. 
:    The *Setup Custom Templates* option copies all the core templates to the `PDF_EXTENDED_TEMPLATES` directory. If you have previously run this setup the core files in your `PDF_EXTENDED_TEMPLATES` directory will be overridden. 
:    Before running this function it's recommended you [review our developer's guide to templating](https://gpdfv4.pv/v4-docs/developer-start-customising/).

Fonts [#fonts](#fonts){#fonts}
:    The font manager allows you to install any TTF or OTF font and use it in your PDFs. There are two required fields when adding a new font:
    1. Unique font name (only alphanumeric characters and spaces must be used)
    1. The URL to the font file (fonts must be uploaded via the Media Library and in TTF or OTF format)

    If the particular font provides different files for bold, italic and bold italics typefaces you can optionally include them. A faux bold, italic or bold italic style will be rendered in the PDF if they are not set. 

:    Once a font is installed you can select it in the PDF settings. If creating a PDF template you also have the option to set the font family directly using CSS (a helpful snippet is provided). 

:    Review our [Font Manager documentation](https://gpdfv4.pv/v4-docs/user-custom-fonts/) for more in-depth details on managing PDF fonts.

Uninstall [#uninstall](#uninstall){#uninstall}
:    This option will completely remove the plugin from your website and clean up the database and file system – it will be as if the software was never installed. **Any custom templates you have will also be deleted**. During the uninstallation the plugin will automatically deactivate and redirect you to the plugins page.
:    When the uninstall button is clicked a warning box will pop up asking you to confirm before continuing.
:    A user must have the `gravityforms_uninstall` capability to complete this action. By default this is only site administrators. If running a multisite only a network super admin can do the uninstallation.

---

### Help Tab [#help](#help){#help}

![Gravity PDF Help Settings Page](https://gpdfv4.pv/app/uploads/2015/10/help-tab.png) Details about the help tab to be refined...
                    