---
ID: 1486
post_title: Template Configuration and Image
author: GravityBot
post_date: 2015-11-03 03:03:30
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/developer-template-configuration-and-image/
published: true
kodex_post_likes_count:
  - "1"
kodex_post_dislikes_count:
  - "1"
---
### Introduction [#introduction](#introduction){#introduction}

Gravity PDF allows users to [set template-specific options](https://gpdfv4.pv/v4-docs/user-setup-pdf/#template-tab) when they configure a Gravity Forms PDF. The template configuration allows you to register supported settings that allow users more granular control over the output of their PDF. You can also include an image preview of your PDF layout to make it easier for users when selecting a template. 

It's worth noting that both the template configuration file and PDF preview image **are optional**. They are **not required** when building custom templates, but **do enhance the user experience**. 

**Jump To**

-   [Template Configuration](#template-configuration)
    -   [Configuration Naming Convention](#configuration-naming-convention)
    -   [Configuration Mark-Up](#configuration-mark-up)
    -   [Configuration Structure](#configuration-structure)
        -   [Core Fields](#core-fields)
        -   [Custom Fields](#custom-fields)

    -   [Template Field Support](#template-field-support)

-   [Template Tutorial – Part 4](#template-tutorial)
    -   [Template Configuration](#template-configuration)
    -   [PDF Custom Field Support](#pdf-custom-field-support)

-   [Image Preview](#image-preview)

### Template Configuration [#template-configuration](#template-configuration){#template-configuration}

![Our Hello World Template File](https://gpdfv4.pv/app/uploads/2015/11/configuration.png) 

Template configuration files are located in the `config` folder inside your [PDF working directory](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/#working-directory). These are PHP files that use [PHP namespaces](http://php.net/manual/en/language.namespaces.php) and contain a class which **must** implement our `Helper_Interface_Config` class (see [PHP Interfaces](http://php.net/manual/en/language.oop5.interfaces.php)). It's also important to correctly name your class and configuration file so it gets auto-loaded by Gravity PDF. It sounds complex at first but you'll find it's surprisingly simple and powerful to use.

#### Configuration Naming Convention [#configuration-naming-convention](#configuration-naming-convention){#configuration-naming-convention}

Your PHP configuration template file should have the same name as your PDF template file. If your template is called `my-super-custom-template.php` then that's what your configuration file will be called (just in the `config` directory).

#### Configuration Mark-Up [#configuration-mark-up](#configuration-mark-up){#configuration-mark-up}

The actual PHP configuration structure is straightforward, but we recommend you base your template off one of the existing configuration files. What's important is to change the files class name to match your PDF template – hyphens should be replaced with underscores. Going back to our `my-super-custom-template.php` example, the class name would be `my_super_custom_template`. Below is a sample for our `my-super-custom-template.php` configuration file:

```{.language-php}
<?php

namespace GFPDFTemplatesConfig;

use GFPDFHelperHelper_Interface_Config;

/**
 * Configuration file for my-super-custom-template.php
 */

/* Exit if accessed directly */
if ( ! defined('ABSPATH') ) {
    exit;
}

/**
 * The configuration class name should be the exact same as the template file name (with hyphens replaced with underscores)
 *
 * For instance, a template called core-simple.php would have a class of "core_simple"
 *
 * This naming convention is very important, otherwise the software cannot correctly load the configuration
 */
class my_super_custom_template implements Helper_Interface_Config {

    /**
     * Return the templates configuration structure which control what extra fields will be shown in the "Template" tab when configuring a form's PDF.
     *
     * @return Array The array, split into core components and custom fields
     * @since 4.0
     */
    public function configuration() {

        return array(

        );
    }
}
```

#### Configuration Structure [#configuration-structure](#configuration-structure){#configuration-structure}

The important part of the above sample is our `configuration` method inside the class. This array will tell Gravity PDF about the custom template fields that it supports. The array is split into two sub-keys: `core` and `fields`. The `core` key allows you to enable built-in fields like headers and footers, while the `fields` key allows you to implement your own fields using our settings API. 

Be aware, defining the supported fields in the configuration is the first part of a two-part exercise. You then need to modify your PDF template to actually support those fields. [We'll discuss supporting your fields later in the article](#template-field-support).

##### Core Fields [#core-fields](#core-fields){#core-fields}

Gravity PDF has a number of built-in template-specific fields you can easily enable. Some of them are only applicable when using the `$pdf->process_html_structure()` method in your custom template, while others can be included in your PDF with a few small tweaks. Below is a sample with core fields enabled:

```{.language-php}
public function configuration() {

    return array(

        /* Enable core fields */
        'core' => array(
            'show_form_title'      => true,
            'show_page_names'      => true,
            'show_html'            => true,
            'show_section_content' => true,
            'show_hidden'          => true,
        ),
    );
}
```

Below are details of all the core fields available to you

show_form_title [#show_form_title](#show_form_title){#show_form_title}
:   Adds a Yes/No field to the template section asking users if they want to shows the Gravity Form title at the beginning of the PDF template.
:   Only applicable when template is using `$pdf->process_html_structure()` in your PDF template.

show_page_names [#show_page_names](#show_page_names){#show_page_names}
:   Adds a Yes/No field to the template section asking users if they want to show Gravity Form page names in the appropriate location within the PDF.
:   Only applicable when template is using `$pdf->process_html_structure()` in your PDF template.

show_html [#show_html](#show_html){#show_html}
:   Adds a Yes/No field to the template section asking users if they want to show Gravity Form HTML fields in the PDF.
:   Only applicable when template is using `$pdf->process_html_structure()` in your PDF template.

show_section_content [#show_section_content](#show_section_content){#show_section_content}
:   Adds a Yes/No field to the template section asking users if they want to show Section break content in the PDF.
:   Only applicable when template is using `$pdf->process_html_structure()` in your PDF template.

show_hidden [#show_hidden](#show_hidden){#show_hidden}
:   Adds a Yes/No field to the template section asking users if they want to show Hidden fields in the PDF
:   Only applicable when template is using `$pdf->process_html_structure()` in your PDF template.

show_empty [#show_empty](#show_empty){#show_empty}
:   Adds a Yes/No field to the template section asking users if they want to show fields that haven't been filled in by the user.
:   Only applicable when template is using `$pdf->process_html_structure()` in your PDF template.

header [#header](#header){#header}
:   Adds a Rich Text Editor to the template section allowing users to include information in the header of the PDF
:   Unless you use `@page` to set your own header, the core header will automatically be included in your PDF.

first_header [#first_header](#first_header){#first_header}
:   Adds a Rich Text Editor to the template section allowing users to include information in a header on the first page of the PDF
:   Unless you use `@page` to set your own header, the core header will automatically be included in your PDF.

footer [#footer](#footer){#footer}
:   Adds a Rich Text Editor to the template section allowing users to include information in the footer of the PDF
:   Unless you use `@page` to set your own footer, the core footer will automatically be included in your PDF.

first_footer [#first_footer](#first_footer){#first_footer}
:   Adds a Rich Text Editor to the template section allowing users to include information in a footer on the first page of the PDF
:   Unless you use `@page` to set your own footer, the core footer will automatically be included in your PDF.

background_image [#background_image](#background_image){#background_image}
:   Adds an upload box to the template section allowing users to upload and select a background image for the PDF
:   Unless you use `@page` to set your own background(-image), the core background image will automatically be included in your PDF.

##### Custom Fields [#custom-fields](#custom-fields){#custom-fields}

Adding your own custom fields is where this feature gets really powerful. Using the `fields` sub-key you can define text, paragraph, rich text, radio buttons, select boxes, colour pickers or upload fields with a few lines of code.

```{.language-php}
public function configuration() {

    return array(

        /* Create custom fields to control the look and feel of a template */
        'fields' => array(
            'prefix_border_colour' => array(
                'id'   => 'prefix_border_colour',
                'name' => __('Field Border Colour', 'gravity-forms-pdf-extended' ),
                'type' => 'color',
                'desc' => __('Control the colour of the field border.', 'gravity-forms-pdf-extended' ),
                'std'  => '#CCCCCC'
            ),
            'prefix_my_custom_radio' => array(
                'id'      => 'prefix_my_custom_radio',
                'name'    => 'My Custom Radio',
                'desc'    => 'This is my field description',
                'type'    => 'radio',
                'options' => array(
                    'Yes'     => __( 'Yes', 'gravity-forms-pdf-extended' ),
                    'No'      => __( 'No', 'gravity-forms-pdf-extended' ),
                ),
                'std'     => __( 'No', 'gravity-forms-pdf-extended' ),              
            ),
        )
    );
}
```

**It's important to use a unique name for the ID (we recommend prefixing them) and ensure your ID and field array key match.** 

Below are details about the most common field attributes that can be used when defining custom template fields:

id [#id](#id){#id}
:   The field ID. This should be unique and we recommend prefixing it.

name [#name](#name){#name}
:   The field label displayed to the user.

type [#type](#type){#type}
:   The field type. Acceptable values include: `text`, `number`, `checkbox`, `multicheck`, `radio`, `select`, `textarea`, `password`, `rich_editor`, `upload`, `color`, `button`, `descriptive_text`, `hook`.

desc [#desc](#desc){#desc}
:   The field description. This will be displayed right below the field.

options [#options](#options){#options}
:   An array of options for use in `multicheck`, `radio`, `select`.

std [#std](#std){#std}
:   The standard value that should be defined when a user hasn't set anything.

class [#class](#class){#class}
:   Add class name to field.

Because only certain options apply to certain fields this isn't an exhaustive list of available attributes, but they are the most common. 

For more details we recommend you review the `/src/helper/Helper_Options_Fields.php` files for samples showing you different field types. You can also see what attributes are supported by a specific field type by reviewing the `/src/helper/Helper_Options.php` – from line 1400 onwards.

#### Custom Field Support [#custom-field-support](#custom-field-support){#custom-field-support}

The `header`, `first_header`, `footer`, `first_footer` and `background` core fields are automagically supported in custom PDF templates (provided you don't override them with your own header/footer or background using `@page`). However, you'll need to update your PDF template to support any custom fields you create. 

To do this, in your PDF template you'll have access a variable named `$settings`. This array contains all the settings a user has defined (using the field ID as the array key) and is where your template settings will be located. Let's have a look at supporting our `prefix_border_colour` custom field.

##### Border Colour Support [#border-colour-support](#border-colour-support){#border-colour-support}

First we need to get the `prefix_border_colour` setting from the `$settings` array. As we mentioned earlier, the `$settings` array is loaded with our PDF user settings which can be accessed by the field ID:

```{.language-php}
$border_colour = ( ! empty( $settings['prefix_border_colour'] ) ) ? $settings['prefix_border_colour'] : '#000'; //check if the setting exists and use it, otherwise fall back to black
```

The `$border_colour` variable will now contain the user-selected colour, or fall back to black. Now we can apply the border colour to an element in our PDF template:

```{.language-html}
    <style>
        .container {
            border: 1px solid <?php echo $border_colour; ?>;            
        }
    </style>
</head>
<body>
   <div class="container">
         This container will have a user-defined border colour.
   </div>
</body>
```

### Template Tutorial – Part 4 [#template-tutorial](#template-tutorial){#template-tutorial}

![Our Hello World template fields](https://gpdfv4.pv/app/uploads/2015/11/hello-world-configuration.png) 

Continuing on from our [Part 3 Hello World Tutorial](https://gpdfv4.pv/v4-docs/developer-php-form-data-array/#template-tutorial), we're going to show you how to create a template configuration with core footer and background support enabled. We'll also add a new field that will determine if meta data should be included in the document.

#### Template Configuration [#template-configuration](#template-configuration){#template-configuration}

First, let's [grab a copy of the basic PDF template PHP mark-up](https://gist.github.com/blueliquiddesigns/3554f5f7885aa08b19dd) and save it in the `config` folder of our [PDF working directory](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/#working-directory). Remember to save the file as `hello-world.php` – the same name we used for our template file. This sample already has class name changed to `hello_world` but you would normally update this to match your template's file name. 

The only area we'll be focusing on is the empty array being returned in the `configuration` method. We'll need to update this to include our two core fields and create our custom field. Let's do the core fields first:

```{.language-php}
public function configuration() {

    return array(
        'core' => array(
            'footer'     => true,
            'background' => true,
        ),
    );
}
```

The [core fields can easily be enabled](#core-fields) by passing their name as the array key with a `true` value. 

We've just told the system we want to enable the footer field and our background image field. If you [edit your Hello World PDF settings in WordPress](https://gpdfv4.pv/v4-docs/user-setup-pdf/), you'll see a new [Template tab](https://gpdfv4.pv/v4-docs/user-setup-pdf/#template-tab) with our two core fields included. The system will automatically parse and store these fields when the PDF settings are saved. 

Including a custom field is a little trickier, but we're just defining array key/value pairs that tell Gravity PDF how to display a field:

```{.language-php}
public function configuration() {

    return array(
        'core' => array(
            'footer'     => true,
            'background' => true,
        ),

        'fields' => array(
            'world_show_meta_data' => array(
                'id' => 'world_show_meta_data',
                'name' => __( 'Show Meta Data', 'world-pdf-template'),              
                'desc' => __( 'When enabled the user IP, timestamp, user agent and source URL will be included in the PDF.', 'world-pdf-template' ),
                'type' => 'radio',
                'options' => array(
                        'Yes'     => __( 'Yes', 'world-pdf-template' ),
                        'No'      => __( 'No', 'world-pdf-template' ),
                ),
                'std' => __( 'No', 'world-pdf-template' )
            )
        ),
    );
}
```

We've just told Gravity PDF about a new radio field called *Show Meta Data* that has Yes/No options. By default the *No* value will be selected and a nice description about what the field does is shown just below the radio buttons. We've also prefixed our field ID with `world_` so we don't clash with any other fields. And because we are conscientious developers we've made all our strings translatable by wrapping them [in the `__()` function](https://developer.wordpress.org/reference/functions/__/). Make sure you only translate the `option` array's value and not the key. 

[Read more about the specifics of each field attribute](#custom-fields). 

If you go back to the [Template tab](https://gpdfv4.pv/v4-docs/user-setup-pdf/#template-tab) you'll now see our two core fields and the *Show Meta Data* field. Go ahead and enable/fill in information for each field then save it. 

[Download the completed configuration template for our Hello World PDF](https://gist.github.com/blueliquiddesigns/b784eb1338c87357cdf8).

#### PDF Custom Field Support [#pdf-custom-field-support](#pdf-custom-field-support){#pdf-custom-field-support}

Now we're capturing and saving the footer, background and meta data toggle from the user we need to update our original *Hello World* PDF template. The core header/footer and background fields will automatically be included, but we'll need to update the PDF template to support our custom field. 

If you haven't been following along with the other tutorials you can [download the current PDF template here](https://gist.github.com/blueliquiddesigns/c7dea5d0953374970f71). 

[If you remember from earlier](#template-field-support) the `$settings` array holds all our custom fields and is where we'll found out meta data setting. To keep our PDF template clean we'll set the settings variables at the beginning of the template (before the HTML).

```{.language-php}
/* Prevent direct access to the template (always good to include this) */
if ( ! class_exists( 'GFForms' ) ) {
    return;
}

/**
 * Load our template-specific settings 
 */
$show_meta_data = ( ! empty( $settings['world_show_meta_data']) ) ? $settings['world_show_meta_data'] : 'No';

?>
```

Here we are checking if our our *Show Meta Data* field exists in the settings array before assigning it to the `$show_meta_data` variable. If it doesn't we'll default to *No*. Now we can do a simple *IF* statement in the `<body>` of our template and output the meta data required:

```{.language-html}
<?php if( $location == 'Titan' ): ?>
    <p>Titan's colony is only recently established. You're one of only 500 people currently living there!</p>
<?php endif; ?>     

<?php if( $show_meta_data == 'Yes' ): ?>
    <p style="font-size: 0.8em;">
        <strong>User IP:</strong> <?php echo $form_data['misc']['ip']; ?><br>
        <strong>Submission Timestamp:</strong> <?php echo $form_data['misc']['date_time']; ?><br>
        <strong>User Agent:</strong> <?php echo $form_data['misc']['user_agent']; ?><br>
        <strong>Source URL:</strong> <?php echo $form_data['misc']['source_url']; ?>
    </p>
<?php endif; ?>
```

If you've enabled the *View Meta Data* option, when you view the *Hello World* PDF you'll see the meta data included. That's all there is to it. You've now added support for all three template-specific fields to the *Hello World* PDF. 

[Download the completed Hello World PDF Template for Part 4](https://gist.github.com/blueliquiddesigns/49ec98ddbb0dd64d42ae).

### Image Preview [#image-preview](#image-preview){#image-preview}

![The preview of the Zadini PDF Template](https://gpdfv4.pv/app/uploads/2015/11/template-image-preview.png) 

When a user selects a PDF template to use from the admin area they'll see a preview of that template if it exists. To add support for your custom PDF template just save a 768x576 PNG to the `images` folder in the [PDF working directory](https://gpdfv4.pv/v4-docs/developer-first-custom-pdf/#working-directory). 

Ensure you use the same name as your custom template when saving the image. For example, an image for our `hello-world.php` template would be named `hello-world.png`.