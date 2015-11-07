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
![The Gravity Forms Editor](https://gpdfv4.pv/app/uploads/2015/10/form-editor.png) 

Only certain form data is important to you. That's why Gravity PDF has a number of ways to filter out the unimportant fields in your generated PDF. 

It's important to note that only certain PDF templates have these filtering options. All the core PDF templates will support the features discussed below, but [premium](#) or [custom templates](https://gpdfv4.pv/v4-docs/developer-start-customising/) may not.

---

### What is Displayed? [#what-is-displayed](#what-is-displayed){#what-is-displayed}

Gravity PDF will adhere to your forms conditional logic when generating a PDF. That means if the conditional logic determines a field (or entire section) should be hidden it won't get displayed on the PDF. Also, if a user doesn't fill in anything for a particular field it won't be displayed either. Both of these settings can be modified – see [#show-hidden-fields](#) and [#show-empty-fields](https://gpdfv4.pv/v4-docs/setup-pdf/#show-empty-fields). 

HTML and Page fields are also hidden by default, but they can be enabled using the [#show-page-names](https://gpdfv4.pv/v4-docs/setup-pdf/#show-page-names) and [#show-html-fields](https://gpdfv4.pv/v4-docs/setup-pdf/#show-html-fields) options. 

You can also choose to show or hide the form's title using the [#show-form-title](https://gpdfv4.pv/v4-docs/setup-pdf/#show-form-title) option.

---

### Hide Specific Field [#hide-specific-field](#hide-specific-field){#what-is-displayed}

![Add 'exclude' field to Gravity Form Field](https://gpdfv4.pv/app/uploads/2015/10/exclude-field.png) 

In certain cases you may not want a particular form field from displaying in the PDF. When that's the case you can add the CSS class `exclude` to a field in the Gravity Forms editor. You can do this by:

1. Navigating to your form's *Form Editor*
1. Select the field you want excluded from the PDF
1. Open the `Appearance` tab and add `exclude` to the `Custom CSS Class` field. If a class is already included ensure you add a space between it and `exclude`
1. Save your form

This technique works for all fields except the *Hidden* field (which doesn't include the *Custom CSS Class* field).
