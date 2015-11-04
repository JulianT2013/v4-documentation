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
---
<img src="https://gpdfv4.pv/app/uploads/2015/10/shortcode-sample.png" alt="The PDF Form List Page" />

Shortcodes have become the backbone of modern WordPress websites and allow the average user to easily publish dynamic content using macros. A macro is simply a shortcut.

Gravity PDF uses shortcodes to help simplify more-complex functionality, like generating PDF links. The only shortcode currently available is <code>[gravitypdf]</code>.

<hr />

<h3>[gravitypdf] shortcode <a href="#gravitypdf-shortcode" title="" id="gravitypdf-shortcode">#gravitypdf-shortcode</a></h3>

This shortcode generates a direct link to a PDF. It has the most use in Gravity Forms <a href="https://www.gravityhelp.com/documentation/article/configuring-confirmations-in-gravity-forms/">confirmations</a> and <a href="https://www.gravityhelp.com/documentation/article/configuring-notifications-in-gravity-forms/">notifications</a>, but can be added in alternate locations when used with the <a href="#entry-attribute">#entry-attribute</a>.

<h4>Security <a href="#security" title="" id="security">#security</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/security-restrictions.png" alt="Access denied security message" />

There are a number of security protocols in place to prevent unauthorised access to PDF documents. Before using this shortcode it's <em>highly recommended</em> you <a href="#">review the documentation detailing PDF security</a>.

<h4>Building the Shortcode <a href="#building-the-shortcode" title="" id="building-the-shortcode">#building-the-shortcode</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/download-pdf-column.png" alt="A &quot;Download PDF&quot; column on the PDF list" />

We wanted to make it as simple as possible to use the <code>[gravitypdf]</code> shortcode in your form's confirmations and notifications. With that in mind, we added a <em>Download PDF</em> column to the <a href="#">PDF form list</a>, which has a sample shortcode for each PDF you have set up. Just copy and paste the shortcode sample to your confirmation or notification and click save<sup id="fnref-1461-1"><a href="#fn-1461-1" rel="footnote">1</a></sup>. The default behaviour is to generate a download link to the PDF with the text <em>Download PDF</em>. Simple!

<h5>Attributes <a href="#shortcode-attributes" title="" id="shortcode-attributes">#shortcode-attributes</a></h5>

The <code>[gravitypdf]</code> shortcode is customisable and there are a number of attributes which can be used to change the default behaviour.

<dl>
<dt>ID (required) <a href="#id-attribute" title="" id="id-attribute">#id-attribute</a></dt>
<dd>
The <code>ID</code> attribute is required and refers to the ID assigned to a particular form's PDF. The easiest way to get the ID is to use the sample shortcode on the <a href="#">PDF form list</a>, as it includes the PDF ID already. However you can find a PDF's ID in the URL when updating the PDF settings. This is denoted by the <code>pid</code> parameter.

<em>/wp-admin/admin.php?page=gf_edit_forms&amp;view=settings&amp;subview=pdf&amp;id=2&amp;pid=<strong>560f2ef799945</strong></em>
</dd>

<dd><em>Example:</em> <code>[gravitypdf id="560f2ef799945"]</code></dd>

<dt>Text (optional) <a href="#text-attribute" title="" id="text-attribute">#text-attribute</a></dt>
<dd>This attribute allows you to change the generated link's text which the end-user will see.</dd>

<dd>If the <code>text</code> attribute isn't present it will default to <em>Download PDF</em>.</dd>

<dd><em>Example:</em> <code>[gravitypdf id="560f2ef799945" text="View PDF"]</code></dd>

<dt>Type (optional) <a href="#type-attribute" title="" id="type-attribute">#type-attribute</a></dt>
<dd>The <code>type</code> attribute has two valid parameters: <code>download</code> and <code>view</code>. When the <code>download</code> option is set, and a user clicks the PDF link, a save dialog box will open – allowing a user to download and then view the PDF locally. When the <code>view</code> option is set the PDF will be rendered in their web browser.</dd>

<dd>If the <code>type</code> attribute isn't present it will default to <code>download</code>.</dd>

<dd><em>Example:</em> <code>[gravitypdf id="560f2ef799945" type="view"]</code> or <code>[gravitypdf id="560f2ef799945" type="view" text="View PDF"]</code></dd>

<dt>Classes (optional) <a href="#classes-attribute" title="" id="classes-attribute">#classes-attribute</a></dt>
<dd>The <code>classes</code> attribute allows you to set a specific class on the generated PDF anchor tag (<code>&lt;a&gt;&lt;/a&gt;</code>). This is useful when you want to style the link a certain way.</dd>

<dd>If the <code>classes</code> attribute isn't present it will default to <code>gravitypdf-download-link</code>.</dd>

<dd><em>Example:</em> <code>[gravitypdf id="560f2ef799945" classes="my-custom-button-class"]</code> or <code>[gravitypdf id="560f2ef799945" classes="my-custom-button-class a-second-class"]</code></dd>

<dt>Entry (semi-optional) <a href="#entry-attribute" title="" id="entry-attribute">#entry-attribute</a></dt>
<dd>When the shortcode is used in Gravity Form confirmations or notifications this attribute can be omitted (as we already know which entry is being processed). However, if you want to use the shortcode outside of that environment you need to pass in the Gravity Form entry ID.</dd>

<dd>Alternatively, instead of passing the entry ID directly to the shortcode you can set the ID via URL parameters (the "query string"). If the <code>entry</code> or <code>lid</code> URL parameters exist its value will be used as the ID (see <a href="#page-confirmation">#page-confirmation</a> for more details).</dd>

<dd><em>Example:</em> <code>[gravitypdf id="560f2ef799945" entry="250"]</code> or <code>[gravitypdf id="560f2ef799945"]</code> with a URL like <code>http://test.com/?entry=250</code></dd>
</dl>

<h4>Confirmation <a href="#confirmation" title="" id="confirmation">#confirmation</a></h4>

Gravity Form <a href="https://www.gravityhelp.com/documentation/article/configuring-confirmations-in-gravity-forms/">Confirmations</a> is what is show to the user after they complete their form. They come in three flavours:

<ol>
<li><a href="#text-confirmation">Text Confirmations</a></li>
<li><a href="#page-confirmation">Page Confirmations</a></li>
<li><a href="#redirect-confirmation">Redirect Confirmations</a></li>
</ol>

We've ensured the <code>[gravitypdf]</code> shortcode works with as little configuration as possible across all confirmation types.

<h5>Text <a href="#text-confirmation" title="" id="text-confirmation">#text-confirmation</a></h5>

<img src="https://gpdfv4.pv/app/uploads/2015/10/text-confirmation.png" alt="The [gravitypdf] shortcode in the Gravity Forms text confirmation" />

The <a href="https://www.gravityhelp.com/documentation/article/configuring-confirmations-in-gravity-forms/#text-confirmations">text confirmation</a> is the simplest Gravity Forms confirmation type. When selected, you can enter a message using the WordPress editor.

To get it functioning you just need to copy and paste the sample shortcode found on the <a href="#">PDF form list</a>.

<h5>Page <a href="#page-confirmation" title="" id="page-confirmation">#page-confirmation</a></h5>

<img src="https://gpdfv4.pv/app/uploads/2015/10/page-redirect.png" alt="The [gravitypdf] shortcode in the Gravity Forms page confirmation" />

The <a href="https://www.gravityhelp.com/documentation/article/configuring-confirmations-in-gravity-forms/#page-confirmations">page confirmation</a> allows you to redirect users to an existing WordPress page. This method is not quite "copy and paste", but it's close.

To get it functioning you need to copy the sample shortcode found on the <a href="#">PDF form list</a> and place it on the WordPress page you're sending your user to. Once done, go back to your confirmation configuration and enable the <code>Pass Field Data Via Query String</code> option. Add <code>entry={entry_id}</code> to the field that appears and click save.

<h5>Redirect <a href="#redirect-confirmation" title="" id="redirect-confirmation">#redirect-confirmation</a></h5>

<img src="https://gpdfv4.pv/app/uploads/2015/10/redirect-confirmation.png" alt="The [gravitypdf] shortcode in the Gravity Forms redirect confirmation" />

The <a href="https://www.gravityhelp.com/documentation/article/configuring-confirmations-in-gravity-forms/#redirect-confirmation">redirect confirmation</a> allows you to send the user to another location upon completing their form. If you choose, you can redirect the user to a PDF.

To get it functioning you just need to copy and paste the sample shortcode found on the <a href="#">PDF form list</a>. When you save the confirmation the shortcode will automatically be converted to a direct PDF link.

<h4>Notifications <a href="#notifications" title="" id="notifications">#notifications</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/notification-example.png" alt="Adding the shortcode to notifications" />

Gravity Form <a href="https://www.gravityhelp.com/documentation/article/configuring-notifications-in-gravity-forms/">Notifications</a> are automated emails sent after the form is submitted. If you would prefer not <a href="#">sending the PDF as an email attachment</a> (usually for <a href="#">security reasons</a>) you can use the <code>[gravitypdf]</code> shortcode and create a direct link to the PDF. Because of the <a href="#">security protocols</a>, this method is very effective when the recipient has a WordPress user account. We don't recommend using it if your forms will be completed by logged out users – add a shortcode to the <a href="#confirmation">confirmation page</a> instead.

<div class="footnotes">
<hr />
<ol>

<li id="fn-1461-1">
The <a href="#page-confirmation">Page confirmation</a> method requires a little extra configuration than text and redirect confirmations.&#160;<a href="#fnref-1461-1" rev="footnote">&#8617;</a>
</li>

</ol>
</div>