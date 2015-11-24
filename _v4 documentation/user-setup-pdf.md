---
ID: 1460
post_title: Setup PDF
author: GravityBot
post_date: 2015-10-12 03:30:14
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-setup-pdf/
published: true
kodex_post_likes_count:
  - "1"
kodex_post_dislikes_count:
  - "1"
---
![Adding new PDF Form](https://gpdfv4.pv/app/uploads/2015/10/Add-new-pdf.png) 

Creating a PDF for an individual Gravity Form is similar to [creating notifications](https://www.gravityhelp.com/documentation/article/configuring-notifications-in-gravity-forms/) (and is found in the same location). There are a lot of options available to users but we've put the most common settings up front. The rest are hidden; split up between four tabs which include:

1. **General** - Common Settings like template, filename, notifications and conditional logic.
1. **Appearance** - Control the paper size and orientation as well as the font type, size and colour.
1. **Template** - The template-specific settings. Different templates can have different options.
1. **Advanced** - Advanced features like PDF security are found here.

**Jump To Section**

* [Locating the PDF Settings](#locating-pdf-settings)
* [Required Fields](#required-fields)
* [Optional Fields](#optional-fields)
    * [General](#general-tab)
    * [Appearance](#appearance-tab)
    * [Template](#template-tab)
    * [Advanced](#advanced-tab)

---

### Locating the PDF Settings [#locating-pdf-settings](#locating-pdf-settings){#locating-pdf-settings}

![PDF Form Settings List](https://gpdfv4.pv/app/uploads/2015/10/PDF-Settings.png) 

The form PDF settings can be accessed by following these steps:

1. Navigating to `Forms -> Forms` in your WordPress admin area.
1. Locate the Gravity Form you want to edit and hover your mouse (or similar device) over that particular row. A list of actions will be revealed; click the `Settings` action.
1. When the page loads you'll see a new tab called `PDF` in the left sidebar. Click that tab.
1. Finally select the `Add New` button to the right of the *Gravity PDF* title.

---

### Required Fields [#required-fields](#required-fields){#required-fields}

There are only two required fields when creating a PDF: the name and filename options. Both appear in the [*General*](#general-tab) tab.

Name [#name](#name){#name}
:    The name field is only used for internal administrative tasks. Its sole purpose is to provide a human-readable identifier for the particular PDF configuration – which can help you distinguish between multiple PDFs in your WordPress admin area. It's best to choose a meaningful easy-to-remember name.

Filename [#filename](#filename){#filename}
:    The filename field is for external use and is what the generated PDF will actually be called when saved.
:    [Gravity Form merge tags](https://www.gravityhelp.com/documentation/article/merge-tags/) are supported.
:    To prevent problems, the following characters will be automatically converted to an underscore when the PDF is generated: `/  " * ? | :`
:    The `.pdf` extension should be excluded from the filename field (but will be automatically removed if you add it).

---

### Optional Fields [#optional-fields](#optional-fields){#optional-fields}

There are a number of optional fields available which give you granular control over how the PDF functions. Each field belongs to one of four tabs. The [*General*](#general-tab) and [*Template*](#template-tab) tabs contain the most common settings.

---

#### General Tab [#general-tab](#general-tab){#general-tab}

![PDF Form Settings General Tab](https://gpdfv4.pv/app/uploads/2015/10/general-tab.png) 

The most common PDF settings are found in the General tab. The required fields [#name](#name) and [#filename](#filename) are also part of this tab.

Template [#template](#template){#template}
:    Select the PDF template that should be used to generated the document. The [global #default-template setting](https://gpdfv4.pv/v4-docs/global-settings/#default-template) controls which template to use by default.
:    Gravity PDF comes with five **completely-free** templates for you to choose from. Upon changing your selection (using the drop down) an image will load showing you what the chosen template looks like. The *Template* tab will also be updated (or removed if it has no options) to reflect the template-specific options.
:    Additional templates can be purchased from our [theme shop](#).
:    Developers with HTML, CSS and a little PHP knowledge can also [create their own designs and layouts](https://gpdfv4.pv/v4-docs/developer-start-customising/). Alternatively, the Gravity PDF team offers [design and integration services](#) for those looking for a custom solution – we can even [integrate exiting PDF documents](#).

Notifications [#notifications](#notifications){#notifications}
:    This setting allows you to automatically attach the PDF to the selected notification(s).
:    The PDF [active state](https://gpdfv4.pv/v4-docs/user-managing-pdfs/#active-toggle) and [#conditional-logic](#conditional-logic) determine if the PDF will be attached to the notification. If one or both of these tests fail no PDF will be attached. This setting **does not** effect the actual notification conditional logic (which determines if the notification should be sent).
:    If there is semi-sensitive user information included in the PDF it's recommended you enable [#pdf-security](#pdf-security) with a strong [#password](#password) (more than 10 characters, with a mix of symbols, numbers and upper and lower case). Password-protected PDFs are encrypted using 128-bit AES.
:    If very sensitive user information is included in the PDF it is recommended you **do not** enable this feature as email can be insecure. Instead [use the `[gravitypdf]` shortcode over HTTPS](#) and enable [#pdf-security](#pdf-security).

Conditional Logic [#conditional-logic](#conditional-logic){#conditional-logic}
:    Conditional logic is a [powerful feature of Gravity Forms](https://www.gravityhelp.com/documentation/article/enable-conditional-logic/) allowing you to show or hide fields in your form based on a user's response. We've extended this behaviour to Gravity PDF, allowing you to enable or disable a PDF if a user responded a specific way.
:    If the conditional logic determines a PDF should be disabled it will not be generated for that entry. The PDF will not be accessible through the `[gravitypdf]` shortcode and will not be attached to notifications. Site administrators won't even be able to access it from the admin area.

---

#### Appearance Tab [#appearance-tab](#appearance-tab){#appearance-tab}

![PDF Form Settings Appearance Tab](https://gpdfv4.pv/app/uploads/2015/10/appearance-tab.png) 

The appearance tab contains fields that control the general look and feel of your PDF. You have granular control over the paper size and orientation, as well as the font, font size / colour and RTL support.

Paper Size [#paper-size](#paper-size){#paper-size}
:    Use this option to set the PDF paper size. This field defaults to the [Default Paper Size](https://gpdfv4.pv/v4-docs/user-global-settings/#paper-size) option in the global settings. Common paper sizes like US Letter and Legal are available. The ISO-standard *A*, *B* and *C* paper sizes, as well as *RA* and *SRA*, are also preloaded.
:    If none of the preloaded options suit you can also select *Custom Paper Size* (see [#custom-paper-size](#custom-paper-size) below) and control the width and height in millimetres or inches.

Custom Paper Size [#custom-paper-size](#custom-paper-size){#custom-paper-size}
:    This field is hidden until you select the *Custom Paper Size* option from the [#paper-size](#paper-size) field. It allows you to control the exact paper size of your document – in millimetres or inches. When displayed, this field is required and only positive numbers are permitted in the width and height inputs.

Orientation [#orientation](#orientation){#orientation}
:    This allows you to change the paper orientation from portrait to landscape. A page displayed in portrait mode is taller than it is wide. Inversely, landscape pages are wider than they are tall.
:    The field defaults to *Portrait*.

Font [#font](#font){#font}
:    Select the font to be used in your PDF. This field defaults to the [Default Font](https://gpdfv4.pv/v4-docs/user-global-settings/#font-type) option in the global settings.
:    If none of the pre-installed fonts suit your needs, additional fonts can be installed using our [Font Installer](https://gpdfv4.pv/v4-docs/user-custom-fonts/).

Font Size [#font-size](#font-size){#font-size}
:    Control the font size used in the PDF. The field defaults to the [Default Font Size](https://gpdfv4.pv/v4-docs/user-global-settings/#font-size) option in the global settings.

Font Colour [#font-colour](#font-colour){#font-colour}
:    Control the font colour used in the PDF. The field defaults to the [Default Font Colour](https://gpdfv4.pv/v4-docs/user-global-settings/#font-colour) option in the global settings.

Reverse Text (RTL) [#rtl](#rtl){#rtl}
:    Control the text direction used in the PDF. The field defaults to the [Reverse Text (RTL)](https://gpdfv4.pv/v4-docs/user-global-settings/#rtl) option in the global settings.

---

#### Template Tab [#template-tab](#template-tab){#template-tab}

![PDF Form Settings Template Tab](https://gpdfv4.pv/app/uploads/2015/10/template-tab.png) 

This tab contains the current template-specific settings. A template may support dozens of custom settings, or none at all (and the tab will be hidden). However, there are a number of in-built settings a template can support, if they so choose. 

Below is a description of the core template settings.

Show Form Title [#show-form-title](#show-form-title){#show-form-title}
:    Optionally display the form name at the beginning of the PDF document.

Show Page Names [#show-page-names](#show-page-names){#show-page-names}
:    When using Gravity Forms' *Page Break* fields you have the option to [name each page using the start page field](https://www.gravityhelp.com/documentation/article/page-break/). When this PDF option is enabled these page names will be displayed in your PDF.

Show HTML Fields [#show-html-fields](#show-html-fields){#show-html-fields}
:    Show your form's HTML fields in the PDF.
:    If your HTML has conditional logic this will be honoured in the PDF. See [#enable-conditional-logic](#enable-conditional-logic) to disable this feature.

Show Section Break Description [#show-section-break-description](#show-section-break-description){#show-section-break-description}
:    The [*Section Break* field](https://www.gravityhelp.com/documentation/article/section-break/) allows you to enter a label and description. By default, a PDF will only show a section break's *label*. Enabling this option will also show the section break description.

Enable Conditional Logic [#enable-conditional-logic](#enable-conditional-logic){#enable-conditional-logic}
:    When this option is enabled, the Gravity Form field conditionals you set in your form will be adhered to in the PDF. This means if a field's conditional logic says it should hidden then it won't be included in the PDF. 
:    This option is useful when you have [#show-empty-fields](#show-empty-fields) enabled.

Show Empty Fields [#show-empty-fields](#show-empty-fields){#show-empty-fields}
:    By default, any field not completed by the user won't be shown in the PDF document. When enabled this option will display all fields, regardless of whether the user filled it out.
:    Conditional logic is honoured on all fields, including empty ones. See [#enable-conditional-logic](#enable-conditional-logic) to disable this feature.

Header [#header](#header){#header}
:    Add a header to your PDF document using the WordPress Editor. You can use the media library to include a simple logo. Or add a more robust three-column table.
:    Gravity Form merge tags can be used in the header.
:    The special tags `{PAGENO}` – which displays the current page number – and `{nbpg}` – which displays the total number of pages in the document – can be used in the header.

First Page Header [#first-page-header](#first-page-header){#first-page-header}
:    When enabled you can add an alternate header to the first page of your PDF document.
:    Gravity Form merge tags can be used in the header.
:    The special tags `{PAGENO}` – which displays the current page number – and `{nbpg}` – which displays the total number of pages in the document – can be used in the header.

Footer [#footer](#footer){#footer}
:    Add a header to your PDF document using the WordPress Editor. You can use the media library to include images. Or add a more robust three-column table that includes the page number and date.
:    Gravity Form merge tags can be used in the footer.
:    The special tags `{PAGENO}` – which displays the current page number – and `{nbpg}` – which displays the total number of pages in the document – can be used in the footer.

First Page Footer [#first-page-footer](#first-page-footer){#first-page-footer}
:    When enabled you can add an alternate footer to the first page of your PDF document.
:    Gravity Form merge tags can be used in the footer.
:    The special tags `{PAGENO}` – which displays the current page number – and `{nbpg}` – which displays the total number of pages in the document – can be used in the footer.

---

#### Advanced Tab [#advanced-tab](#advanced-tab){#advanced-tab}

![PDF Form Settings Advanced Tab](https://gpdfv4.pv/app/uploads/2015/10/advanced-tab.png) 

The advanced tab allows you to control the PDF security (which includes password protection). You can also change the image DPI and the format to PDF/A-1b or PDF/X-1a.

Format [#format](#format){#format}
:    This allows you to change the PDF to one of the ISO-standard PDF/A-1b or PDF/X-1a formats.
:    The PDF/A-1b standard is designed for long-term archiving and is 100% self-contained. All the information necessary for displaying the document is embedded in the file.
:    The PDF/X-1a standard is designed to facilitate printing. Like the PDF/A-1b standard, the document is 100% self-contained but has the added restriction that all images need to be CMYK or spot colours. The software will automatically convert any images to CMYK.
:    Both the PDF/A-1b and PDF/X-1a standards do not allow transparency, which means you cannot use watermarks or PNG images with alpha channel transparency. Additionally, the [#pdf-security](#pdf-security) option is disabled – which includes the [#password](#password) and [#privileges](#privileges) fields.

Enable PDF Security [#pdf-security](#pdf-security){#pdf-security}
:    When the [#format](#format) is set to *Standard* you have the option to enable PDF security. This allows you to set a password to access the PDF, or control the end-user document privileges.

Password [#password](#password){#password}
:    When [#pdf-security](#pdf-security) is enabled you have the option to password-protect your PDF documents. [Mergetag](https://www.gravityhelp.com/documentation/article/merge-tags/) usage is allowed.
:    Leave this field blank if you don't want to set a password (useful if you only want to control the end-user [#privileges](#privileges))

Privileges [#privileges](#privileges){#privileges}
:    You can restrict what the end user does with the PDF by removing privileges. The following privileges are available:
     1. **Annotate**: Add or modify text annotations.
     1. **Assemble**: Allow users to insert, delete or rotate pages.
     1. **Copy**: Allow users to copy and pasting content from the document.
     1. **Extract**: Allow users to split or extract pages from the document.
     1. **Fill Forms**: Allow users to fill in any active form field elements.
     1. **Printing - High Resolution**: Allow high quality printing and PDF re-distilling.
     1. **Printing - Low Resolution**: Low-resolution printing will generate a bitmapped image of the document that is suitable for personal use. High-quality reproduction and re-distilling is disabled. If you don't want the user to print at all remove both *Printing* privileges.
     1. **Modify**: If this privilege is removed, document modifications is disabled. However, copying, extracting content and printing are allowed.

Image DPI [#image-dpi](#image-dpi){#image-dpi}
:    Adjust the image DPI (Dots Per Inch). By default this is set to 96. If professionally printing you should set this to *300* and change the [#format](#format) to *PDF/X-1a*.

Always Save PDF [#save-pdf](#save-pdf){#save-pdf}
:    By default, when a new Gravity Form entry is submitted a PDF is only ever saved to disk when the [#notifications](#notifications) feature is enabled. When this setting is active this option is very useful in conjunction with the `gfpdf_post_pdf_save` filter – which can be used to copy the generated PDF to an alternate location.