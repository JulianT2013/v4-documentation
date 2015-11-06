---
ID: 5241
post_title: Helper Parameters
author: GravityBot
post_date: 2015-11-04 02:04:00
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/development-helper-parameters/
published: true
---
### Introduction [#introduction](#introduction){#introduction}

We've included a number of techniques to assist you when creating custom PDF templates. From viewing the `$form_data` array in an easy-to-read format, to direct paths to the [PDF working directory](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/#working-directory).

#### URL Parameters [#url-parameters](#url-parameters){#url-parameters}

When viewing a Gravity PDF in your browser there's a couple of URL parameters that will assist you. A URL parameter is simply a value added to your URL which Gravity PDF can read. It might look like this:

```
https://gravitypdf.com/pdf/12i0afjafwijww212/?name=value
```

The URL parameter is the `name=value` pair after the question mark. 

data=1
:    ![Preview of the 'data' attribute](https://gpdfv4.pv/app/uploads/2015/11/data.png)
:    The data URL parameter is used to display the full output of the $form_data array in your browser. This is very useful when [creating your PDF template using PHP only](https://gpdfv4.pv/v4-docs/developer-php-form-data-array/).
:    Usage: `https://gravitypdf.com/pdf/12i0afjafwijww212/?data=1`

html=1
:    ![Preview of the 'html' attribute](https://gpdfv4.pv/app/uploads/2015/11/html.png)
:    The HTML URL parameter is used to display the generated PDF template's HTML mark-up. What's display is the HTML that gets sent to the PDF software and it has all the PHP and merge tag formatting complete. This is very useful to in debugging layout issues. 
:    Usage: `https://gravitypdf.com/pdf/12i0afjafwijww212/?html=1`

template={name}
:    ![Preview of the 'template' attribute](https://gpdfv4.pv/app/uploads/2015/11/template.png)
:    The template URL parameter allows you to quickly swap between different PDF template files. The `{name}` value needs to be substituted for the PHP template name (with the `.php` extension removed).
:    Usage: `https://gravitypdf.com/pdf/12i0afjafwijww212/?template=hello-world`

#### Useful Paths and URLs [#useful-paths-and-urls](#useful-paths-and-urls){#useful-paths-and-urls}

When creating custom PDF templates it's often useful to include external CSS files and images, however you don't want to use a fixed path or URL. Instead, you should use a PHP constant or function that contains the correct path or URL. 

PDF_TEMPLATE_LOCATION
:    This is a constant that contains the path to the [PDF working directory](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/#working-directory) or, in multisite installations, the path to the [individual multisite working directory](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/#multisite-structure). We use this often to reference images or other PHP files on the host machine. 
:    Usage: `<img src="<?php echo PDF_TEMPLATE_LOCATION; ?>images/hello-world.png" width="400" />`

PDF_TEMPLATE_URL_LOCATION
:    This is a constant that contains the URL to the [PDF working directory](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/#working-directory) or, for multisite installations, the URL to the [individual multisite working directory](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/#multisite-structure). This is useful if you want to provide a link to a file on the host machine.
:    Usage: `<a href="<?php echo PDF_TEMPLATE_URL_LOCATION; ?>images/hello-world.png">View Sample</a>`

ABSPATH
:    A WordPress constant that references to the directory in which WordPress is installed. This is less useful that the other methods (usually you don't store files in the root directory) but it's good to know about.
:    Usage: `<img src="<?php echo ABSPATH; ?>logo.png" width="400" />`

wp_upload_dir()
:    A [WordPress function](https://codex.wordpress.org/Function_Reference/wp_upload_dir) that returns path and URL information about the uploads directory. 
:    Usage:
     ```
     $upload_dir = wp_upload_dir();
     echo '<img src="' . $upload_dir['path'] . '2015/04/hello-world.png" width="400" />';
     ```
