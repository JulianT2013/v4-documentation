---
ID: 1711
post_title: Importing / Exporting and Duplicating
author: Jake Jackson
post_date: 2015-10-21 04:10:38
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/importing-exporting-and-duplicating/
published: true
---
![When forms are duplicated PDF settings go with it](https://gpdfv4.pv/app/uploads/2015/10/sticky-glue-pdf-settings.png)

When using a Gravity Form add-on like Survey or PayPal have you noticed how those form-specific add-on settings aren't super glued to your form? What we mean by that is if you duplicate your form the add-on form settings aren't duplicated with it. The same goes for when you export your form and then import it on another WordPress site. None of the add-on configuration is imported with the form. 

We feel this behaviour is counterintuitive, and we didn't want to force our users to redo all their PDF configuration if a form was duplicated or exported. We strongly believed the PDF configuration settings should function like confirmations and notifications, so much so that we built our own form settings [CRUD](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) interface to do just that. 

In layman's terms this means Gravity PDF form settings **are** like super glue. If you duplicate a form any PDF settings will be duplicated. If you export a form and then import it the PDF settings will be included. 





