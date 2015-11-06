---
ID: 1487
post_title: Template Hierarchy
author: GravityBot
post_date: 2015-11-04 00:56:48
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/developer-template-hierarchy/
published: true
---
### Introduction [#introduction](#introduction){#introduction}

We [touched on the template hierarchy](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/#template-hierarchy) when you created your first custom PDF template, but it's a little more involved – especially for Multisite installations. It's also not just limited to PDF templates, and the core configuration and image preview files can be overridden as well.

### Standard WordPress Installation [#standard-wordpress-install](#standard-wordpress-install){#standard-wordpress-install}

![WordPress Standard Template Hierarchy](https://gpdfv4.pv/app/uploads/2015/11/WordPress-Standard-Hierarchy.png)

On a standard WordPress installation the template hierarchy is straightforward. Files in the [PDF working directory](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/#working-directory) override templates that ship with the plugin – provided they have the same name. [When you prepare your website for custom PDF templates](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/#preparing-the-infrastructure) all the plugin's template files are copied over to your PDF working directory so you can override the settings if you wish. It's straightforward and easy. 

### Multisite WordPress Installation [#multisite-wordpress-install](#multisite-wordpress-install){#multisite-wordpress-install}

![WordPress Multisite Template Hierarchy](https://gpdfv4.pv/app/uploads/2015/11/WordPress-Multisite-Hierarchy.png)

To allow more flexibility with PDF templates, multisite installations add another layer to the template hierarchy. Each website of a multisite installation [gets its own PDF working directory](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/#multisite-structure) so different site can have their own PDF templates that won't be included elsewhere. Individual site templates override any global templates in the `PDF_EXTENDED_TEMPLATES` directory (which apply to all multisite installations), which in turn override the core Gravity PDF plugins (like in a [standard WordPress installation](#standard-wordpress-install)).