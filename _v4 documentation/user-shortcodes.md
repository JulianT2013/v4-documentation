---
ID: 1461
post_title: Shortcodes
author: GravityBot
post_date: 2015-10-15 03:10:59
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-shortcodes/
published: true
kodex_post_likes_count:
  - "0"
kodex_post_dislikes_count:
  - "0"
---
![The PDF Form List Page](https://gpdfv4.pv/app/uploads/2015/10/shortcode-sample.png) 

Shortcodes have become the backbone of modern WordPress websites and allow the average user to easily publish dynamic content using macros. A macro is simply a shortcut. 

Gravity PDF uses shortcodes to help simplify more-complex functionality, like generating PDF links. The only shortcode currently available is `[gravitypdf]`.

---

### [gravitypdf] shortcode [#gravitypdf-shortcode](#gravitypdf-shortcode){#gravitypdf-shortcode}

This shortcode generates a direct link to a PDF. It has the most use in Gravity Forms [confirmations](https://www.gravityhelp.com/documentation/article/configuring-confirmations-in-gravity-forms/) and [notifications](https://www.gravityhelp.com/documentation/article/configuring-notifications-in-gravity-forms/), but can be added in alternate locations when used with the [#entry-attribute](#entry-attribute).

#### Security [#security](#security){#security}

![Access denied security message](https://gpdfv4.pv/app/uploads/2015/10/security-restrictions.png) 

There are a number of security protocols in place to prevent unauthorised access to PDF documents. Before using this shortcode it's *highly recommended* you [review the documentation detailing PDF security](https://gpdfv4.pv/v4-docs/user-pdf-security/).

#### Building the Shortcode [#building-the-shortcode](#building-the-shortcode){#building-the-shortcode}

![A "Download PDF" column on the PDF list](https://gpdfv4.pv/app/uploads/2015/10/download-pdf-column.png) 

We wanted to make it as simple as possible to use the `[gravitypdf]` shortcode in your form's confirmations and notifications. With that in mind, we added a *Download PDF* column to the [PDF form list](https://gpdfv4.pv/v4-docs/user-managing-pdfs/#download-shortcode), which has a sample shortcode for each PDF you have set up. Just copy and paste the shortcode sample to your confirmation or notification and click save[^1]. The default behaviour is to generate a download link to the PDF with the text *Download PDF*. Simple!

##### Attributes [#shortcode-attributes](#shortcode-attributes){#shortcode-attributes}

The `[gravitypdf]` shortcode is customisable and there are a number of attributes which can be used to change the default behaviour.

ID (required) [#id-attribute](#id-attribute){#id-attribute}
:    The `ID` attribute is required and refers to the ID assigned to a particular form's PDF. The easiest way to get the ID is to use the sample shortcode on the [PDF form list](https://gpdfv4.pv/v4-docs/user-managing-pdfs/), as it includes the PDF ID already. However you can find a PDF's ID in the URL when updating the PDF settings. This is denoted by the `pid` parameter. 

    */wp-admin/admin.php?page=gf_edit_forms&view=settings&subview=pdf&id=2&pid=**560f2ef799945***
:    *Example:* `[gravitypdf id="560f2ef799945"]`

Name (optional) [#name-attribute](#name-attribute){#name-attribute}
:    This attribute doesn't effect the shortcode in any way, but does allow you to quickly determine which PDF it references. 

Text (optional) [#text-attribute](#text-attribute){#text-attribute}
:    This attribute allows you to change the generated link's text which the end-user will see.
:    If the `text` attribute isn't present it will default to *Download PDF*.
:    *Example:* `[gravitypdf id="560f2ef799945" text="View PDF"]`

Type (optional) [#type-attribute](#type-attribute){#type-attribute}
:    The `type` attribute has two valid parameters: `download` and `view`. When the `download` option is set, and a user clicks the PDF link, a save dialog box will open – allowing a user to download and then view the PDF locally. When the `view` option is set the PDF will be rendered in their web browser.
:    If the `type` attribute isn't present it will default to `download`.
:    *Example:* `[gravitypdf id="560f2ef799945" type="view"]` or `[gravitypdf id="560f2ef799945" type="view" text="View PDF"]`

Classes (optional) [#classes-attribute](#classes-attribute){#classes-attribute}
:    The `classes` attribute allows you to set a specific class on the generated PDF anchor tag (`<a></a>`). This is useful when you want to style the link a certain way.
:    If the `classes` attribute isn't present it will default to `gravitypdf-download-link`.
:    *Example:* `[gravitypdf id="560f2ef799945" classes="my-custom-button-class"]` or `[gravitypdf id="560f2ef799945" classes="my-custom-button-class a-second-class"]`

Print (optional) [#print-attribute](#print-attribute){#print-attribute}
:    The `print` attribute will automatically open a print dialog box when the PDF is viewed. 
:    *Example:* `[gravitypdf id="560f2ef799945" print="true"]`

Entry (semi-optional) [#entry-attribute](#entry-attribute){#entry-attribute}
:    When the shortcode is used in Gravity Form confirmations or notifications this attribute can be omitted (as we already know which entry is being processed). However, if you want to use the shortcode outside of that environment you need to pass in the Gravity Form entry ID.
:    Alternatively, instead of passing the entry ID directly to the shortcode you can set the ID via URL parameters (the "query string"). If the `entry` or `lid` URL parameters exist its value will be used as the ID (see [#page-confirmation](#page-confirmation){#page-confirmation} for more details).
:    *Example:* `[gravitypdf id="560f2ef799945" entry="250"]` or `[gravitypdf id="560f2ef799945"]` with a URL like `http://test.com/?entry=250`

#### Confirmation [#confirmation](#confirmation){#confirmation}

Gravity Form [Confirmations](https://www.gravityhelp.com/documentation/article/configuring-confirmations-in-gravity-forms/) is what is show to the user after they complete their form. They come in three flavours:

1. [Text Confirmations](#text-confirmation)
1. [Page Confirmations](#page-confirmation)
1. [Redirect Confirmations](#redirect-confirmation)

We've ensured the `[gravitypdf]` shortcode works with as little configuration as possible across all confirmation types.

##### Text [#text-confirmation](#text-confirmation){#text-confirmation}

![The [gravitypdf] shortcode in the Gravity Forms text confirmation](https://gpdfv4.pv/app/uploads/2015/10/text-confirmation.png) 

The [text confirmation](https://www.gravityhelp.com/documentation/article/configuring-confirmations-in-gravity-forms/#text-confirmations) is the simplest Gravity Forms confirmation type. When selected, you can enter a message using the WordPress editor. 

To get it functioning you just need to copy and paste the sample shortcode found on the [PDF form list](#).

##### Page [#page-confirmation](#page-confirmation){#page-confirmation}

![The [gravitypdf] shortcode in the Gravity Forms page confirmation](https://gpdfv4.pv/app/uploads/2015/10/page-redirect.png) 

The [page confirmation](https://www.gravityhelp.com/documentation/article/configuring-confirmations-in-gravity-forms/#page-confirmations) allows you to redirect users to an existing WordPress page. This method is not quite "copy and paste", but it's close. 

To get it functioning you need to copy the sample shortcode found on the [PDF form list](https://gpdfv4.pv/v4-docs/user-managing-pdfs/#download-shortcode) and place it on the WordPress page you're sending your user to. Once done, go back to your confirmation configuration and enable the `Pass Field Data Via Query String` option. Add `entry={entry_id}` to the field that appears and click save.

##### Redirect [#redirect-confirmation](#redirect-confirmation){#redirect-confirmation}

![The [gravitypdf] shortcode in the Gravity Forms redirect confirmation](https://gpdfv4.pv/app/uploads/2015/10/redirect-confirmation.png) 

The [redirect confirmation](https://www.gravityhelp.com/documentation/article/configuring-confirmations-in-gravity-forms/#redirect-confirmation) allows you to send the user to another location upon completing their form. If you choose, you can redirect the user to a PDF. 

To get it functioning you just need to copy and paste the sample shortcode found on the [PDF form list](https://gpdfv4.pv/v4-docs/user-managing-pdfs/#download-shortcode). When you save the confirmation the shortcode will automatically be converted to a direct PDF link.

#### Notifications [#notifications](#notifications){#notifications}

![Adding the shortcode to notifications](https://gpdfv4.pv/app/uploads/2015/10/notification-example.png) 

Gravity Form [Notifications](https://www.gravityhelp.com/documentation/article/configuring-notifications-in-gravity-forms/) are automated emails sent after the form is submitted. If you would prefer not [sending the PDF as an email attachment](https://gpdfv4.pv/v4-docs/user-setup-pdf/#notifications) (usually for security reasons) you can use the `[gravitypdf]` shortcode and create a direct link to the PDF. 

Because of the [security protocols](https://gpdfv4.pv/v4-docs/user-pdf-security/), this method is very effective when the recipient has a WordPress user account. We don't recommend using it if your forms will be completed by logged out users – add a shortcode to the [confirmation page](#confirmation) instead.

[^1]: The [Page confirmation](#page-confirmation) method requires a little extra configuration than text and redirect confirmations.