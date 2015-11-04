---
ID: 1483
post_title: Start Customising
author: GravityBot
post_date: 2015-10-28 02:29:29
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/developer-start-customising/
published: true
---
### Before You Begin [#before-you-begin](#before-you-begin){#before-you-begin}

This section of the documentation is written towards developers. Assumed knowledge of WordPress basics, like [action and filter hooks](https://codex.wordpress.org/Plugin_API), with a solid PHP foundation and HTML / CSS is expected. If that last sentence just went over your head [get in touch with our friendly team](#) and we can discuss a solution tailored for you. 

### Overview [#overview](#overview){#overview}

We've attempted to make Gravity PDF as developer-friendly as possible. That means there are actions and filters placed all through the software so you can tweak the functionality as you see fit. You can also control the exact look and feel of the generated PDFs using custom PDF templates, which are created using HTML/CSS and a bit of PHP knowledge. 

### Custom Templates [#custom-templates](#custom-templates){#custom-templates}

The majority of our developer documentation will be targeted at creating custom PDF templates. You'll learn to:

* Setup Gravity PDF so it utilises custom templates.
* The different techniques for displaying Gravity Form data in the PDFs – using [mergetags](https://www.gravityhelp.com/documentation/article/merge-tags/) or a PHP array .
* How to utilise a PDF configuration file to [create template-specific settings](https://gpdfv4.pv/v4-docs/user-setup-pdf/#template-tab).
* Adding a PDF template image so users can see what the custom template looks like. 
* How the PDF hierarchy works so you can override core templates.

[Tell me more about setting up custom PDF templates](#).

#### Supported PDF Features [#supported-pdf-features](#supported-pdf-features){#supported-pdf-features}

Along with learning the ins and outs to create a template and configuration file, we'll go into detail about the common features you can use when laying out your PDF using HTML/CSS. We'll cover:

* Supported HTML / CSS: it's not like your web browser.
* Background Images
* Headers and Footers
* Watermarks
* Rounded Corners 
* Images
* Tables
* Floats
* Fixed Positioning
* PageBreaks

[Tell me more about designing PDFs](#).

For those developers looking for in-depth knowledge about the PDF engine, mPDF, that Gravity PDF uses we recommend you [review the mPDF user and reference guide](http://mpdf1.com/manual/index.php).

### Actions / Filters [#actions-filters](#actions-filters){#actions-filters}

We've worked hard to document as many of the filters and actions available in Gravity PDF. From changing the output of particular Gravity Form fields to controlling the PDF security (we call it middleware). If you need a new filter or action added [please open a new ticket on GitHub](https://github.com/GravityPDF/gravity-forms-pdf-extended/issues).

[Tell me more about Gravity PDF actions and filters](#).