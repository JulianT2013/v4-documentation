---
ID: 1484
post_title: Merge Tags and Conditional Shortcodes
author: Jake Jackson
post_date: 2015-11-02 01:24:43
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/developer-mergetags-and-conditional-shortcodes/
published: true
---
### Introduction [#introduction](#introduction){#introduction}

Gravity Forms has a [powerful marco they call *Merge Tags*](https://www.gravityhelp.com/documentation/article/merge-tags/) which allows you to display form content, user meta data, post data and other information like the entry submission date. There's also [conditional shortcodes](https://www.gravityhelp.com/documentation/article/shortcodes/#conditional-shortcode) which you can use to allow simple *IF* statements. Both merge tags and conditional shortcodes are supported in PDF templates and together they make a powerful combination. 

### Template Tutorial – Part 2 [#template-tutorial](#template-tutorial){#template-tutorial}

In [Template Tutorial – Part 1](#) we showed you the very minimum needed to create a PDF template. In part 2 we're going to utilise merge tags and conditional shortcodes in a template. Before you begin you will need to download the [Gravity Form](https://gpdfv4.pv/app/uploads/2015/11/hello-world-gravity-form.json) we'll be working with and [import it into your website](https://www.gravityhelp.com/documentation/article/importing-a-form-into-gravity-forms/). Once done, submit a new entry for the newly-imported *Hello World* form.

#### Merge Tags [#mergetags](#mergetags){#mergetags}

Gravity Form *field* merge tags use the format `{[Field Name]:[field_id]}`. Keep in mind, the *Field Name* isn't required and advanced fields have a slightly different format. 

When you first start using merge tags, the simplest way to write them is by editing one of your [form's notifications](https://www.gravityhelp.com/documentation/article/configuring-notifications-in-gravity-forms/) and then using the merge tag selector to the right of the *Message* field. Just copy and paste the merge tag to your PDF template. 

Once you're comfortable with how certain fields are formatted it becomes easy to write your own: `{Email:5}`, `{:5}`, `{First Name:4.3}` or `{:4.3}`.

In our `hello-world.php` template we're going to add a new line below the `<h1>` tag and include our form's merge tags:

```{.language-html}
<h1>Hello World</h1>

<p>You're from {Where do you live?:3}, {Name (First):1.3}? How cool is that!</p>
```

Now when you view the *Hello World* PDF for the entry you created earlier it will include the Gravity Forms data. All Gravity Form fields can be displayed in the PDF this way. 

#### Conditional Shortcodes [#conditional-shortcodes](#conditional-shortcodes){#conditional-shortcodes}

Conditional Shortcodes allow you to output different content in the PDF based on a user's response. The structure of the shortcode is relatively simple, with four required attributes including: `action`, `merge_tag`, `condition` and `value`. [See the Gravity Forms documentation for full details on its usage](https://www.gravityhelp.com/documentation/article/shortcodes/#conditional-shortcode).

In our `hello-world.php` template we're going to add conditional shortcodes that outputs a small fact about where the user lives. If a user selects `Earth` only the Earth fact will be displayed. Below the `<p>...</p>` HTML we'll add the following:

```{.language-html}
<p>You're from {Where do you live?:3}, {Name (First):1.3}? How cool is that!</p>

[gravityforms action="conditional" merge_tag="{Where do you live?:3}" condition="is" value="Earth"]
	<p>The birth-rate on Earth has dropped almost 25% in the past 50 years due to colonisation of the solar system.</p>
[/gravityforms]

[gravityforms action="conditional" merge_tag="{Where do you live?:3}" condition="is" value="Moon"]
	<p>The lunar colony was first established in 2115 with a population of 200. Now it supports over 900,000 people.</p>
[/gravityforms]

[gravityforms action="conditional" merge_tag="{Where do you live?:3}" condition="is" value="Mars"]
	<p>Mars was the second body to be colonised in the solar system in 2135, 20 years after the moon.</p>
[/gravityforms]

[gravityforms action="conditional" merge_tag="{Where do you live?:3}" condition="is" value="Titan"]
	<p>Titan's colony is only recently established. You're one of only 500 people currently living there!</p>
[/gravityforms]	

```

When you view the *Hello World* PDF now it will conditionally display one of the four facts. Then [edit the *Hello World* entry](https://www.gravityhelp.com/documentation/article/entry-detail/) and changing the `Where do you live?` field value. When you view the PDF again a different fact will be displayed.

[Download the completed Hello World PDF template for Part 2](https://gist.github.com/blueliquiddesigns/6c0a5268fa23ba51a285).