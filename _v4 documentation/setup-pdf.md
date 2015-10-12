---
ID: 1460
post_title: Setup PDF
author: Jake Jackson
post_date: 2015-10-12 03:30:14
post_excerpt: ""
layout: v4_docs
permalink: https://gpdfv4.pv/v4-docs/setup-pdf/
published: true
---
Creating a PDF for an individual Gravity Form is similar to [creating notifications](https://www.gravityhelp.com/documentation/article/configuring-notifications-in-gravity-forms/) (and is found in the same location). There are a lot of options available to users but we've put the most common settings up front. The rest are hidden; split up between four tabs, including:

1. General - Common Settings like template, filename, notifications and conditional logic
1. Appearance - Control the paper size and orientation as well as the font type, size and colour
1. Template - The template-specific settings. Different templates can have different options.
1. Advanced - Advanced features like PDF security are found here.

**Jump To Section**

* [Locating the PDF Settings](#locating)
* [Required Fields](#required-fields)
* [Optional Fields](#optional-fields)
    - [General](#general-tab)
    - [Appearance](#appearance-tab)
    - [Template](#template)
    - [Advanced](#advanced)

### Locating the PDF Settings [(#locating)](#locating){#locating}

The form PDF settings can be accessed by following these steps:

1. Navigating to `Forms -> Forms` in your WordPress admin area. 
1. Locate the Gravity Form you want to edit and hover your mouse (or similar device) over that particular row. A list of actions will be revealed; click the `Settings` action.
1. When the page loads you'll see a new tab called `PDF` in the left sidebar. Click that tab.
1. Finally select the `Add New` button to the right of the *Gravity PDF* title.

### Required Fields [(#required-fields)](#required-fields){#required-fields}

There are only two required fields when creating a PDF: the name and filename options. Both appear in the [*General*](#general-tab) tab. 

Name [(#name)](#name){#name}
:    The name field is only used for internal administrative tasks. Its sole purpose is to provide a human-readable identifier for the particular PDF configuration, which can help you distinguish between multiple PDFs in your WordPress admin area. It's best to choose a meaningful easy-to-remember name.

Filename [(#filename)](#filename){#filename}
:    The filename field is for external use and is what the generated PDF will actually be called when saved. 
:    You can include the entry information in the filename using [Gravity Form mergetags](https://www.gravityhelp.com/documentation/article/merge-tags/).
:    To prevent problems, the following characters will be automatically converted to an underscore when the PDF is generated: `/ \ " * ? | :`
:    The `.pdf` extension should be excluded from the filename field (but will be automatically removed if you add it).

### Optional Fields [(#optional-fields)](#optional-fields){#optional-fields}

There are a number of optional fields available which give you granular control over how the PDF functions. Each field belongs to one of four tabs. The [*General*](#general-tab) and [*Template*](#template-tab) tabs contain the most common settings.

#### General Tab [(#general-tab)](#general-tab){#general-tab}

The most common PDF settings are found in the General tab. The required fields [#name](#name) and [#filename](#filename) are also part of this tab.

Template [(#template)](#template){#template}
:     Select the PDF template that should be used to generated the document. The [global #default-template setting](https://gpdfv4.pv/v4-docs/global-settings/#default-template) controls which template to use by default. 
:    Gravity PDF comes with five **completely-free** templates for you to choose from. Upon changing your selection (using the drop down) an image will load showing you what the chosen template looks like. The *Template* tab will also be updated (or removed if it has no options) to reflect the template-specific options.
:    Additional templates can be purchased from our [theme shop](#). 
:    Developers with HTML, CSS and a little PHP knowledge can also [create their own designs and layouts](#). Alternatively, the Gravity PDF team offers [design and integration services](#) for those looking for a custom solution – we can even [integrate an exiting PDF document](#).

Notifications [(#notifications)](#notifications){#notifications}
:    This setting allows you to automatically attach the PDF to the selected notification(s). 
:    The PDF [active state](#) and [#conditional-logic](#conditional-logic) determine if the PDF will be attached to the notification. If one or both of these tests fail no PDF will be attached. This setting **does not** effect the actual notification conditional logic (which determines if the notification should be sent).
:    If very sensitive user information is included in the PDF it is recommended you **do not** enable this feature as email can be insecure. Instead [use the `[gravitypdf]` shortcode over HTTPS](#). 
:    If there is semi-sensitive user information, but you still want to send the document via email, it's recommended you enable [#pdf-security](#pdf-security) with a strong [#password](#password) (more than 10 characters, with a mix of symbols, numbers and upper and lower case). Password-protected PDFs are encrypted using 128-bit AES.

Conditional Logic [(#conditional-logic)](#conditional-logic){#conditional-logic}
:    Conditional logic is a [powerful feature of Gravity Forms](https://www.gravityhelp.com/documentation/article/enable-conditional-logic/) allowing you to show or hide fields in your form based on a user's response. We've extended this behaviour to Gravity PDF, allowing you to enable or disable a PDF if a user responded a specific way. 
:    If the conditional logic determines a PDF should be disabled it will not be generated for that entry. The PDF will not be accessible through the `[gravitypdf]` shortcode and will not be attached to notifications. Site administrators won't even be able to access it from the admin area. 

#### Appearance Tab [(#appearance-tab)](#appearance-tab){#appearance-tab}

Paper Size [(#paper-size)](#paper-size){#paper-size}
:    info

Orientation [(#orientation)](#orientation){#orientation}
:    info

Font [(#font)](#font){#font}
:    info

Font Size [(#font-size)](#font-size){#font-size}
:    info

Font Colour [(#font-colour)](#font-colour){#font-colour}
:    info

Reverse Text (RTL) [(#rtl)](#rtl){#rtl}
:    info

#### Template Tab [(#template-tab)](#template-tab){#template-tab}

#### Advanced Tab [(#advanced-tab)](#advanced-tab){#advanced-tab}