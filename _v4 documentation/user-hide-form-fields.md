---
ID: 1471
post_title: Hide Form Fields
author: GravityBot
post_date: 2015-10-21 02:20:59
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-hide-form-fields/
published: true
---
<img src="https://gpdfv4.pv/app/uploads/2015/10/form-editor.png" alt="The Gravity Forms Editor" />

Only certain form data is important to you. That's why Gravity PDF has a number of ways to filter out the unimportant fields in your generated PDF.

It's important to note that only certain PDF templates have these filtering options. All the core PDF templates will support the features discussed below, but <a href="#">premium</a> or <a href="#">custom templates</a> may not.

<hr />

<h3>What is Displayed? <a href="#what-is-displayed" title="" id="what-is-displayed">#what-is-displayed</a></h3>

Gravity PDF will adhere to your forms conditional logic when generating a PDF. That means if the conditional logic determines a field (or entire section) should be hidden it won't get displayed on the PDF. Also, if a user doesn't fill in anything for a particular field it won't be displayed either. Both of these settings can be modified – see <a href="#">#show-hidden-fields</a> and <a href="https://gpdfv4.pv/v4-docs/setup-pdf/#show-empty-fields">#show-empty-fields</a>.

HTML and Page fields are also hidden by default, but they can be enabled using the <a href="https://gpdfv4.pv/v4-docs/setup-pdf/#show-page-names">#show-page-names</a> and <a href="https://gpdfv4.pv/v4-docs/setup-pdf/#show-html-fields">#show-html-fields</a> options.

You can also choose to show or hide the form's title using the <a href="https://gpdfv4.pv/v4-docs/setup-pdf/#show-form-title">#show-form-title</a> option.

<hr />

<h3>Hide Specific Field <a href="#hide-specific-field" title="" id="hide-specific-field">#hide-specific-field</a></h3>

<img src="https://gpdfv4.pv/app/uploads/2015/10/exclude-field.png" alt="Add 'exclude' field to Gravity Form Field" title="" class="aligncenter" />

In certain cases you may not want a particular form field from displaying in the PDF. When that's the case you can add the CSS class <code>exclude</code> to a field in the Gravity Forms editor. You can do this by:

<ol>
<li>Navigating to your form's <em>Form Editor</em> </li>
<li>Select the field you want excluded from the PDF</li>
<li>Open the <code>Appearance</code> tab and add <code>exclude</code> to the <code>Custom CSS Class</code> field. If a class is already included ensure you add a space between it and <code>exclude</code></li>
<li>Save your form</li>
</ol>

This technique works for all fields except the <em>Hidden</em> field (which doesn't include the <em>Custom CSS Class</em> field).