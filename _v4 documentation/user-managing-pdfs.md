---
ID: 1459
post_title: Managing PDFs
author: GravityBot
post_date: 2015-10-19 02:27:51
post_excerpt: ""
layout: v4_docs
permalink: >
  https://gpdfv4.pv/v4-docs/user-managing-pdfs/
published: true
---
<img src="https://gpdfv4.pv/app/uploads/2015/10/pdf-list.png" alt="A look at a form's PDF list" />

When you begin taking advantage of <a href="https://gpdfv4.pv/v4-docs/setup-pdf/#conditional-logic">conditional logic</a>, or <a href="#">premium</a> and <a href="#">custom</a> templates, one PDF per form just isn't enough. That's why we've built an AJAXified PDF list to help you activate / deactivate, duplicate and delete your PDFs – all without a page reload. You can also add new PDFs or edit existing ones (it's not AJAX-powered though). The user interface is similar to the confirmation and notification lists so you should feel right at home.

To access the <em>Managing PDFs</em> page see <a href="https://gpdfv4.pv/v4-docs/setup-pdf/#locating">Locating Your PDF Settings</a>.

<hr />

<h3>List Columns <a href="#columns" title="" id="columns">#columns</a></h3>

<img src="https://gpdfv4.pv/app/uploads/2015/10/column-list.png" alt="The list column names" />

The PDF list contains four columns which provide an overview of the PDFs currently configured for your Gravity Form.

<dl>
<dt>Name <a href="#name" title="" id="name">#name</a></dt>
<dd>This column displays the internal PDF <a href="https://gpdfv4.pv/v4-docs/setup-pdf/#name">name</a>. It also functions as the "actions" column. By hovering over the row the <code>Edit</code>, <code>Duplicate</code> and <code>Delete</code> actions will appear in this column.</dd>

<dt>Download Shortcode <a href="#download-shortcode" title="" id="download-shortcode">#download-shortcode</a></dt>
<dd>This column displays a sample shortcode that generates a download link for the PDF. Use it in the Gravity Form confirmations or notifications. <a href="https://gpdfv4.pv/v4-docs/shortcodes/">See our shortcode documentation</a> for more details about the <code>[gravitypdf]</code> shortcode.</dd>

<dt>Template <a href="#template" title="" id="template">#template</a></dt>
<dd>The selected PDF template will be displayed in this column. Along with the name, the template's group will also be displayed. For instance, any template that ships with the software is apart of the <code>Core</code> group. This is useful when you start creating <a href="#">custom PDF templates</a>.</dd>

<dd>If you've run the <a href="https://gpdfv4.pv/v4-docs/global-settings/#custom-templates">Setup Custom Templates</a> tool the text "User Templates" may appear. This means the template is being loaded from the user templates location instead of the core plugin files. See the <a href="#">Custom Templates documentation</a> for more details.</dd>

<dd>PDF templates may also require a specific version of Gravity PDF. If the version requirements aren't met a notice will be displayed in this column.</dd>

<dt>Notifications <a href="#notifications" title="" id="notifications">#notifications</a></dt>
<dd>If you've configured the PDF to attach to any of the form's notifications a list of those notifications will show in this column.</dd>
</dl>

<hr />

<h3>Actions <a href="#actions" title="" id="actions">#actions</a></h3>

There a five main actions available to you when managing your PDFs. They are:

<ol>
<li><a href="#add">Add</a></li>
<li><a href="#edit">Edit</a></li>
<li><a href="#active-toggle">Activate / Deactivate</a></li>
<li><a href="#duplicate">Duplicate</a></li>
<li><a href="#delete">Delete</a></li>
</ol>

The Edit, Duplicate and Delete actions will appear in the <a href="#name">#name</a> column while hovering over the row.

<h4>Add <a href="#add" title="" id="add">#add</a></h4>

New PDFs can be added by clicking the <code>Add New</code> button, which is located to the right of the <em>Gravity PDF</em> page heading. <a href="https://gpdfv4.pv/v4-docs/setup-pdf/">See our Setup PDF documentation</a> for more details on adding new PDFs.

<h4>Edit <a href="#edit" title="" id="edit">#edit</a></h4>

Click a PDFs <em>Edit</em> action to modify an existing PDF configuration. <a href="https://gpdfv4.pv/v4-docs/setup-pdf/">See our Setup PDF documentation</a> for more in-depth details on what each PDF setting does.

<h4>Activate / Deactivate PDFs <a href="#active-toggle" title="" id="active-toggle">#active-toggle</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/toggles.png" alt="Active and deactivated toggles" />

PDFs can be <strong>completely disabled</strong> by using the activate/deactivate toggle – located to the left of the <code>Name</code> column. Once a PDF has been deactivated users and administrators will no longer be able to access the document. The PDF will not be attached to email notifications, and its shortcode won't generate a link.

<h4>Duplicate <a href="#duplicate" title="" id="duplicate">#duplicate</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/duplcate.png" alt="The UI shown when duplicating PDFs" />

You can duplicate an existing PDF configuration by clicking the <em>Duplicate</em> action. This action will happen in the background without the page reloading and once done you'll see a copy of the PDF added to the list.

<h4>Delete <a href="#delete" title="" id="delete">#delete</a></h4>

<img src="https://gpdfv4.pv/app/uploads/2015/10/delete.png" alt="The warning shown when deleting PDFs" />

You can delete an existing PDF configuration by clicking the <em>Delete</em> action. A warning box will pop up asking you to confirm before a PDF is deleted. This action will happen in the background without the page reloading.