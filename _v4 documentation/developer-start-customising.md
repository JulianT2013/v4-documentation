---
ID: 1483
post_title: Start Customising
author: GravityBot
post_date: 2015-10-28 02:29:29
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/documentation/v4/developer-start-customising/
published: true
kodex_post_likes_count:
  - "1"
kodex_post_dislikes_count:
  - "1"
---
### Before You Begin [#before-you-begin](#before-you-begin){#before-you-begin}

This section of the documentation is written towards developers. Assumed knowledge of WordPress basics, like [action and filter hooks](https://codex.wordpress.org/Plugin_API), with a solid PHP foundation and HTML / CSS is expected. If that last sentence just went over your head [get in touch with our friendly team](#) and we can discuss a solution tailored for you. 

### Overview [#overview](#overview){#overview}

We've attempted to make Gravity PDF as developer-friendly as possible. That means there are actions and filters placed all through the software so you can tweak the functionality as you see fit. You can also control the exact look and feel of the generated PDFs using custom PDF templates, which are created using HTML/CSS and a bit of PHP knowledge. 

### Custom Templates [#custom-templates](#custom-templates){#custom-templates}

![Sample of a custom PDF template](https://gpdfv4.pv/app/uploads/2015/11/pdf-template-code-sample.png)

The majority of our developer documentation will be targeted at creating custom PDF templates. You'll learn to:

* Setup Gravity PDF so it utilises custom templates.
* The different techniques for displaying Gravity Form data in the PDFs – using [mergetags](https://www.gravityhelp.com/documentation/article/merge-tags/) or a PHP array.
* How to utilise a PDF configuration file to [create template-specific settings](https://gpdfv4.pv/v4-docs/user-setup-pdf/#template-tab).
* Adding a PDF template image so users can see what the custom template looks like. 
* How the PDF hierarchy works so you can override core templates.

[Tell me more about setting up custom PDF templates](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/).

#### Supported PDF Features [#supported-pdf-features](#supported-pdf-features){#supported-pdf-features}

![Sample of a PDF showing off the HTML support](https://gpdfv4.pv/app/uploads/2015/11/pdf-features.png)

Along with learning the ins and outs to create a template and configuration file, we'll go into detail about the common features you can use when laying out your PDF using HTML/CSS. We'll cover:

* [Supported HTML / CSS](https://gpdfv4.pv/v4-docs/developer-supported-html-and-css/): it's not like your web browser.
* [Background Images](https://gpdfv4.pv/v4-docs/developer-backgrounds/)
* [Headers and Footers](https://gpdfv4.pv/v4-docs/developer-headers-and-footers/)
* [Watermarks](https://gpdfv4.pv/v4-docs/developer-watermarks/)
* [Rounded Corners](https://gpdfv4.pv/v4-docs/developer-rounded-corners/)
* [Images](https://gpdfv4.pv/v4-docs/developer-images/)
* [Tables](https://gpdfv4.pv/v4-docs/developer-tables/)
* [Floats](https://gpdfv4.pv/v4-docs/developer-floats/)
* [Fixed Positioning](https://gpdfv4.pv/v4-docs/developer-positioning/)
* [Page Breaks](https://gpdfv4.pv/v4-docs/developer-pagebreaks/)

For those developers looking for in-depth knowledge about the PDF engine, mPDF, which Gravity PDF uses we recommend you [review the mPDF user and reference guide](http://mpdf1.com/manual/index.php).

### Actions / Filters [#actions-filters](#actions-filters){#actions-filters}

![Sample of a filter available](https://gpdfv4.pv/app/uploads/2015/11/filters.png)

We've worked hard to document as many of the filters and actions available in Gravity PDF. This includes changing the output of particular Gravity Form fields to controlling the PDF security (we call it middleware). If you need a new filter or action added [please open a new ticket on GitHub](https://github.com/GravityPDF/gravity-pdf/issues).

[Tell me more about Gravity PDF actions and filters](#).