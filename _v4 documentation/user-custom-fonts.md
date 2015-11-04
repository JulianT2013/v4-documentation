---
ID: 1457
post_title: Custom Fonts
author: GravityBot
post_date: 2015-10-19 23:53:03
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-custom-fonts/
published: true
---
<img src="https://gpdfv4.pv/app/uploads/2015/10/font-manager.png" alt="Font Manager" />

Gravity PDF is pre-installed with over 30 different fonts which support a large percentage of languages worldwide. For languages that aren't supported out of the box additional fonts can be installed to fill the gap. Of course, this feature isn't limited to additional language support. You can use it to enhance the overall look and feel of your PDF, or allow you to meet a company's style guide.

<hr />

<h3>Font Installer <a href="#font-installer">#font-installer</a></h3>

The font installer is found in the plugin setting's <a href="https://gpdfv4.pv/v4-docs/global-settings/#tools"><em>Tools</em> tab</a> – navigate to <code>Forms -&gt; Settings -&gt; PDF -&gt; Tools</code> in your WordPress admin area – and is accessed by selecting the <em>Manage Fonts</em> button. <strong>Jump To Section</strong>

<ul>
<li><a href="#adding-font">Adding a Font</a></li>
<li><a href="#editing-font">Editing a Font</a></li>
<li><a href="#deleting-font">Deleting a Font</a></li>
</ul>

<hr />

<h4>Adding a Font <a href="#adding-font">#adding-font</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/add-font.png" alt="Add Font Interface" />

Click the <em>Add Font</em> "plus" icon and an empty form will be displayed where you can name and upload your font files. The form fields available include:

<dl>
<dt>Font Name (required) <a href="#font-name">#font-name</a></dt>
<dd>This is the name that gets displayed through all Gravity PDF's interfaces and is used when setting the font in your PDF. It doesn't have to be the same name as your font but it's a good idea to keep them similar.</dd>

<dd>Due to how the PDF software handles fonts only alphanumeric characters and spaces are allowed in the name (A-Z / 0-9).</dd>

<dt>Regular (required) <a href="#regular">#regular</a></dt>
<dd>This field references the main font file for your <a href="https://en.wikipedia.org/wiki/Typeface">typeface</a>. Use the <em>Select Font</em> button to open your media library and upload a <code>.ttf</code> or <code>.otf</code> font file. Once uploaded, select your font and press the blue <em>Select Font</em> button in the bottom right hand corner of your screen.</dd>

<dd>While the field accepts a URL to the font, the file <strong>must</strong> be uploaded through your media library for it to be correctly loaded in the PDF software. External font links will not work. This rule also applies to the <a href="#bold">#bold</a>, <a href="#italics">#italics</a> and <a href="#bold-italics">#bold-italics</a> fields.</dd>

<dt>Bold (optional) <a href="#bold">#bold</a></dt>
<dd>If your <a href="https://en.wikipedia.org/wiki/Typeface">typeface</a> includes a bold version of your font you can add it here. Use the <em>Select Font</em> button to open your media library and select the font.</dd>

<dd>This field is optional and if not provided the PDF software will mimic bold when referenced. However, you will get a better result if a bold font file is installed.</dd>

<dt>Italics (optional) <a href="#italics">#italics</a></dt>
<dd>If your <a href="https://en.wikipedia.org/wiki/Typeface">typeface</a> includes an italics version of your font you can add it here. Use the <em>Select Font</em> button to open your media library and select the font.</dd>

<dd>This field is optional and if not provided the PDF software will mimic italics when referenced. However, you will get a better result if an italics font file is installed.</dd>

<dt>Bold Italics (optional) <a href="#bold-italics">#bold-italics</a></dt>
<dd>If your <a href="https://en.wikipedia.org/wiki/Typeface">typeface</a> includes a bold-italics version of your font you can add it here. Use the <em>Select Font</em> button to open your media library and select the font.</dd>

<dd>This field is optional and if not provided the PDF software will mimic bold-italics when referenced. However, you will get a better result if a bold-italics font file is installed.</dd>

<dt>Custom Template Usage <a href="#custom-template-usage">#custom-template-usage</a></dt>
<dd>This is a read-only field which displays a simple CSS statement for use in <a href="#">custom PDF templates</a>. If you want the entire PDF to use your custom font then change the <a href="https://gpdfv4.pv/v4-docs/setup-pdf/#font">Font setting</a> when you setup your PDF.</dd>
</dl>

<hr />

<h4>Editing a Font <a href="#editing-font">#editing-font</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/edit-font.png" alt="Edit Font Interface" />

Once you've installed a custom font or two you'll see a list of those fonts when you open the <em>Font Manager</em>. You can edit the font by clicking on its name, updating the details and clicking <em>Save</em>. Simple!

<hr />

<h4>Deleting a Font <a href="#deleting-font">#deleting-font</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/delete-font.png" alt="Delete Font Interface" />

In the <em>Font Manager</em> there is a blue trash can icon to the right of each installed font. When you hover over the icon it will turn red and after being clicked a warning box will pop up asking you to confirm before a font is deleted.

<em>Deleting a font from the Font Manager does not delete the font files you've uploaded in your media library.</em>