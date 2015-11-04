---
ID: 1460
post_title: Setup PDF
author: GravityBot
post_date: 2015-10-12 03:30:14
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-setup-pdf/
published: true
---
<img src="https://gpdfv4.pv/app/uploads/2015/10/Add-new-pdf.png" alt="Adding new PDF Form" />

Creating a PDF for an individual Gravity Form is similar to <a href="https://www.gravityhelp.com/documentation/article/configuring-notifications-in-gravity-forms/">creating notifications</a> (and is found in the same location). There are a lot of options available to users but we've put the most common settings up front. The rest are hidden; split up between four tabs which include:

<ol>
<li><strong>General</strong> - Common Settings like template, filename, notifications and conditional logic.</li>
<li><strong>Appearance</strong> - Control the paper size and orientation as well as the font type, size and colour.</li>
<li><strong>Template</strong> - The template-specific settings. Different templates can have different options.</li>
<li><strong>Advanced</strong> - Advanced features like PDF security are found here.</li>
</ol>

<strong>Jump To Section</strong>

<ul>
<li><a href="#locating-pdf-settings">Locating the PDF Settings</a></li>
<li><a href="#required-fields">Required Fields</a></li>
<li><a href="#optional-fields">Optional Fields</a>

<ul>
<li><a href="#general-tab">General</a></li>
<li><a href="#appearance-tab">Appearance</a></li>
<li><a href="#template-tab">Template</a></li>
<li><a href="#advanced-tab">Advanced</a></li>
</ul></li>
</ul>

<hr />

<h3>Locating the PDF Settings <a href="#locating-pdf-settings" title="" id="locating-pdf-settings">#locating-pdf-settings</a></h3>

<img src="https://gpdfv4.pv/app/uploads/2015/10/PDF-Settings.png" alt="PDF Form Settings List" />

The form PDF settings can be accessed by following these steps:

<ol>
<li>Navigating to <code>Forms -&gt; Forms</code> in your WordPress admin area. </li>
<li>Locate the Gravity Form you want to edit and hover your mouse (or similar device) over that particular row. A list of actions will be revealed; click the <code>Settings</code> action.</li>
<li>When the page loads you'll see a new tab called <code>PDF</code> in the left sidebar. Click that tab.</li>
<li>Finally select the <code>Add New</code> button to the right of the <em>Gravity PDF</em> title.</li>
</ol>

<hr />

<h3>Required Fields <a href="#required-fields" title="" id="required-fields">#required-fields</a></h3>

There are only two required fields when creating a PDF: the name and filename options. Both appear in the <a href="#general-tab"><em>General</em></a> tab.

<dl>
<dt>Name <a href="#name" title="" id="name">#name</a></dt>
<dd>The name field is only used for internal administrative tasks. Its sole purpose is to provide a human-readable identifier for the particular PDF configuration – which can help you distinguish between multiple PDFs in your WordPress admin area. It's best to choose a meaningful easy-to-remember name.</dd>

<dt>Filename <a href="#filename" title="" id="filename">#filename</a></dt>
<dd>The filename field is for external use and is what the generated PDF will actually be called when saved.</dd>

<dd><a href="https://www.gravityhelp.com/documentation/article/merge-tags/">Gravity Form mergetags</a> are supported.</dd>

<dd>To prevent problems, the following characters will be automatically converted to an underscore when the PDF is generated: <code>/ \ " * ? | :</code></dd>

<dd>The <code>.pdf</code> extension should be excluded from the filename field (but will be automatically removed if you add it).</dd>
</dl>

<hr />

<h3>Optional Fields <a href="#optional-fields" title="" id="optional-fields">#optional-fields</a></h3>

There are a number of optional fields available which give you granular control over how the PDF functions. Each field belongs to one of four tabs. The <a href="#general-tab"><em>General</em></a> and <a href="#template-tab"><em>Template</em></a> tabs contain the most common settings.

<hr />

<h4>General Tab <a href="#general-tab" title="" id="general-tab">#general-tab</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/general-tab.png" alt="PDF Form Settings General Tab" />

The most common PDF settings are found in the General tab. The required fields <a href="#name">#name</a> and <a href="#filename">#filename</a> are also part of this tab.

<dl>
<dt>Template <a href="#template" title="" id="template">#template</a></dt>
<dd>Select the PDF template that should be used to generated the document. The <a href="https://gpdfv4.pv/v4-docs/global-settings/#default-template">global #default-template setting</a> controls which template to use by default.</dd>

<dd>Gravity PDF comes with five <strong>completely-free</strong> templates for you to choose from. Upon changing your selection (using the drop down) an image will load showing you what the chosen template looks like. The <em>Template</em> tab will also be updated (or removed if it has no options) to reflect the template-specific options.</dd>

<dd>Additional templates can be purchased from our <a href="#">theme shop</a>.</dd>

<dd>Developers with HTML, CSS and a little PHP knowledge can also <a href="#">create their own designs and layouts</a>. Alternatively, the Gravity PDF team offers <a href="#">design and integration services</a> for those looking for a custom solution – we can even <a href="#">integrate exiting PDF documents</a>.</dd>

<dt>Notifications <a href="#notifications" title="" id="notifications">#notifications</a></dt>
<dd>This setting allows you to automatically attach the PDF to the selected notification(s).</dd>

<dd>The PDF <a href="#">active state</a> and <a href="#conditional-logic">#conditional-logic</a> determine if the PDF will be attached to the notification. If one or both of these tests fail no PDF will be attached. This setting <strong>does not</strong> effect the actual notification conditional logic (which determines if the notification should be sent).</dd>

<dd>If there is semi-sensitive user information included in the PDF it's recommended you enable <a href="#pdf-security">#pdf-security</a> with a strong <a href="#password">#password</a> (more than 10 characters, with a mix of symbols, numbers and upper and lower case). Password-protected PDFs are encrypted using 128-bit AES.</dd>

<dd>If very sensitive user information is included in the PDF it is recommended you <strong>do not</strong> enable this feature as email can be insecure. Instead <a href="#">use the <code>[gravitypdf]</code> shortcode over HTTPS</a> and enable <a href="#pdf-security">#pdf-security</a>.</dd>

<dt>Conditional Logic <a href="#conditional-logic" title="" id="conditional-logic">#conditional-logic</a></dt>
<dd>Conditional logic is a <a href="https://www.gravityhelp.com/documentation/article/enable-conditional-logic/">powerful feature of Gravity Forms</a> allowing you to show or hide fields in your form based on a user's response. We've extended this behaviour to Gravity PDF, allowing you to enable or disable a PDF if a user responded a specific way.</dd>

<dd>If the conditional logic determines a PDF should be disabled it will not be generated for that entry. The PDF will not be accessible through the <code>[gravitypdf]</code> shortcode and will not be attached to notifications. Site administrators won't even be able to access it from the admin area.</dd>
</dl>

<hr />

<h4>Appearance Tab <a href="#appearance-tab" title="" id="appearance-tab">#appearance-tab</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/appearance-tab.png" alt="PDF Form Settings Appearance Tab" />

The appearance tab contains fields that control the general look and feel of your PDF. You have granular control over the paper size and orientation, as well as the font, font size / colour and RTL support.

<dl>
<dt>Paper Size <a href="#paper-size" title="" id="paper-size">#paper-size</a></dt>
<dd>Use this option to set the PDF paper size. This field defaults to the <a href="#">Default Paper Size</a> option in the global settings. Common paper sizes like US Letter and Legal are available. The ISO-standard <em>A</em>, <em>B</em> and <em>C</em> paper sizes, as well as <em>RA</em> and <em>SRA</em>, are also preloaded.</dd>

<dd>If none of the preloaded options suit you can also select <em>Custom Paper Size</em> (see <a href="#custom-paper-size">#custom-paper-size</a> below) and control the width and height in millimetres or inches.</dd>

<dt>Custom Paper Size <a href="#custom-paper-size" title="" id="custom-paper-size">#custom-paper-size</a></dt>
<dd>This field is hidden until you select the <em>Custom Paper Size</em> option from the <a href="#paper-size">#paper-size</a> field. It allows you to control the exact paper size of your document – in millimetres or inches. When displayed, this field is required and only positive numbers are permitted in the width and height inputs.</dd>

<dt>Orientation <a href="#orientation" title="" id="orientation">#orientation</a></dt>
<dd>This allows you to change the paper orientation from portrait to landscape. A page displayed in portrait mode is taller than it is wide. Inversely, landscape pages are wider than they are tall.</dd>

<dd>The field defaults to <em>Portrait</em>.</dd>

<dt>Font <a href="#font" title="" id="font">#font</a></dt>
<dd>Select the font to be used in your PDF. This field defaults to the <a href="#">Default Font</a> option in the global settings.</dd>

<dd>If none of the pre-installed fonts suit your needs, additional fonts can be installed using our <a href="#">Font Installer</a>.</dd>

<dt>Font Size <a href="#font-size" title="" id="font-size">#font-size</a></dt>
<dd>Control the font size used in the PDF. The field defaults to the <a href="#">Default Font Size</a> option in the global settings.</dd>

<dt>Font Colour <a href="#font-colour" title="" id="font-colour">#font-colour</a></dt>
<dd>Control the font colour used in the PDF. The field defaults to the <a href="#">Default Font Colour</a> option in the global settings.</dd>

<dt>Reverse Text (RTL) <a href="#rtl" title="" id="rtl">#rtl</a></dt>
<dd>Control the text direction used in the PDF. The field defaults to the <a href="#">Reverse Text (RTL)</a> option in the global settings.</dd>
</dl>

<hr />

<h4>Template Tab <a href="#template-tab" title="" id="template-tab">#template-tab</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/template-tab.png" alt="PDF Form Settings Template Tab" />

This tab contains the current template-specific settings. A template may support dozens of custom settings, or none at all (and the tab will be hidden). However, there are a number of in-built settings a template can support, if they so choose. Below is a description of the core template settings.

<dl>
<dt>Show Form Title <a href="#show-form-title" title="" id="show-form-title">#show-form-title</a></dt>
<dd>Optionally display the form name at the beginning of the PDF document.</dd>

<dt>Show Page Names <a href="#show-page-names" title="" id="show-page-names">#show-page-names</a></dt>
<dd>When using Gravity Forms' <em>Page Break</em> fields you have the option to <a href="https://www.gravityhelp.com/documentation/article/page-break/">name each page using the start page field</a>. When this PDF option is enabled these page names will be displayed in your PDF.</dd>

<dt>Show HTML Fields <a href="#show-html-fields" title="" id="show-html-fields">#show-html-fields</a></dt>
<dd>Show your form's HTML fields in the PDF.</dd>

<dd>If your HTML has conditional logic this will be honoured in the PDF. See <a href="#show-hidden-fields">#show-hidden-fields</a> to disable this feature.</dd>

<dt>Show Section Break Description <a href="#show-section-break-description" title="" id="show-section-break-description">#show-section-break-description</a></dt>
<dd>The <a href="https://www.gravityhelp.com/documentation/article/section-break/"><em>Section Break</em> field</a> allows you to enter a label and description. By default, a PDF will only show a section break's <em>label</em>. Enabling this option will also show the section break description.</dd>

<dt>Show Hidden Fields <a href="#show-hidden-fields" title="" id="show-hidden-fields">#show-hidden-fields</a></dt>
<dd><strong>NEEDS REVIEW</strong></dd>

<dt>Show Empty Fields <a href="#show-empty-fields" title="" id="show-empty-fields">#show-empty-fields</a></dt>
<dd>By default, any field not completed by the user won't be shown in the PDF document. When enabled this option will display all fields, regardless of whether the user filled it out.</dd>

<dd>Conditional logic is honoured on all fields, including empty ones. See <a href="#show-hidden-fields">#show-hidden-fields</a> to disable this feature.</dd>

<dt>Header <a href="#header" title="" id="header">#header</a></dt>
<dd>Add a header to your PDF document using the WordPress Editor. You can use the media library to include a simple logo. Or add a more robust three-column table.</dd>

<dd>Gravity Form mergetags can be used in the header.</dd>

<dd>The special tags <code>{PAGENO}</code> – which displays the current page number – and <code>{nbpg}</code> – which displays the total number of pages in the document – can be used in the header.</dd>

<dt>First Page Header <a href="#first-page-header" title="" id="first-page-header">#first-page-header</a></dt>
<dd>When enabled you can add an alternate header to the first page of your PDF document.</dd>

<dd>Gravity Form mergetags can be used in the header.</dd>

<dd>The special tags <code>{PAGENO}</code> – which displays the current page number – and <code>{nbpg}</code> – which displays the total number of pages in the document – can be used in the header.</dd>

<dt>Footer <a href="#footer" title="" id="footer">#footer</a></dt>
<dd>Add a header to your PDF document using the WordPress Editor. You can use the media library to include images. Or add a more robust three-column table that includes the page number and date.</dd>

<dd>Gravity Form mergetags can be used in the footer.</dd>

<dd>The special tags <code>{PAGENO}</code> – which displays the current page number – and <code>{nbpg}</code> – which displays the total number of pages in the document – can be used in the footer.</dd>

<dt>First Page Footer <a href="#first-page-footer" title="" id="first-page-footer">#first-page-footer</a></dt>
<dd>When enabled you can add an alternate footer to the first page of your PDF document.</dd>

<dd>Gravity Form mergetags can be used in the footer.</dd>

<dd>The special tags <code>{PAGENO}</code> – which displays the current page number – and <code>{nbpg}</code> – which displays the total number of pages in the document – can be used in the footer.</dd>
</dl>

<hr />

<h4>Advanced Tab <a href="#advanced-tab" title="" id="advanced-tab">#advanced-tab</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/advanced-tab.png" alt="PDF Form Settings Advanced Tab" />

The advanced tab allows you to control the PDF security (which includes password protection). You can also change the image DPI and the format to PDF/A-1b or PDF/X-1a.

<dl>
<dt>Format <a href="#format" title="" id="format">#format</a></dt>
<dd>This allows you to change the PDF to one of the ISO-standard PDF/A-1b or PDF/X-1a formats.</dd>

<dd>The PDF/A-1b standard is designed for long-term archiving and is 100% self-contained. All the information necessary for displaying the document is embedded in the file.</dd>

<dd>The PDF/X-1a standard is designed to facilitate printing. Like the PDF/A-1b standard, the document is 100% self-contained but has the added restriction that all images need to be CMYK or spot colours. The software will automatically convert any images to CMYK.</dd>

<dd>Both the PDF/A-1b and PDF/X-1a standards do not allow transparency, which means you cannot use watermarks or PNG images with alpha channel transparency. Additionally, the <a href="#pdf-security">#pdf-security</a> option is disabled – which includes the <a href="#password">#password</a> and <a href="#privileges">#privileges</a> fields.</dd>

<dt>Enable PDF Security <a href="#pdf-security" title="" id="pdf-security">#pdf-security</a></dt>
<dd>When the <a href="#format">#format</a> is set to <em>Standard</em> you have the option to enable PDF security. This allows you to set a password to access the PDF, or control the end-user document privileges.</dd>

<dt>Password <a href="#password" title="" id="password">#password</a></dt>
<dd>When <a href="#pdf-security">#pdf-security</a> is enabled you have the option to password-protect your PDF documents. <a href="https://www.gravityhelp.com/documentation/article/merge-tags/">Mergetag</a> usage is allowed.</dd>

<dd>Leave this field blank if you don't want to set a password (useful if you only want to control the end-user <a href="#privileges">#privileges</a>)</dd>

<dt>Privileges <a href="#privileges" title="" id="privileges">#privileges</a></dt>
<dd>
You can restrict what the end user does with the PDF by removing privileges. The following privileges are available:

<ol>
<li><strong>Annotate</strong>: Add or modify text annotations.</li>
<li><strong>Assemble</strong>: Allow users to insert, delete or rotate pages.</li>
<li><strong>Copy</strong>: Allow users to copy and pasting content from the document. </li>
<li><strong>Extract</strong>: Allow users to split or extract pages from the document. </li>
<li><strong>Fill Forms</strong>: Allow users to fill in any active form field elements.</li>
<li><strong>Printing - High Resolution</strong>: Allow high quality printing and PDF re-distilling.</li>
<li><strong>Printing - Low Resolution</strong>: Low-resolution printing will generate a bitmapped image of the document that is suitable for personal use. High-quality reproduction and re-distilling is disabled. If you don't want the user to print at all remove both <em>Printing</em> privileges. </li>
<li><strong>Modify</strong>: If this privilege is removed, document modifications is disabled. However, copying, extracting content and printing are allowed.</li>
</ol>
</dd>

<dt>Image DPI <a href="#image-dpi" title="" id="image-dpi">#image-dpi</a></dt>
<dd>Adjust the image DPI (Dots Per Inch). By default this is set to 96. If professionally printing you should set this to <em>300</em> and change the <a href="#format">#format</a> to <em>PDF/X-1a</em>.</dd>

<dt>Always Save PDF <a href="#save-pdf" title="" id="save-pdf">#save-pdf</a></dt>
<dd>By default, when a new Gravity Form entry is submitted a PDF is only ever saved to disk when the <a href="#notifications">#notifications</a> feature is enabled. When this setting is active this option is very useful in conjunction with the <code>gfpdf_post_pdf_save</code> filter – which can be used to copy the generated PDF to an alternate location.</dd>
</dl>